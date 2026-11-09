---
title: Cadre de confidentialité avancé agrégé
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2023-11-15T15:21:08Z'
  id: 360018515798
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/360018515798
---
> **En bref :** depuis iOS 14.5+ et le déploiement de la fonctionnalité ATT par Apple, les annonceurs utilisent le cadre de confidentialité avancée agrégée (CAA) pour contrôler la disponibilité des données d'attribution de niveau utilisateur à partir de la plateforme.

<div id="aggregated-advanced-privacy-aap-framework" />

## Cadre Aggregated Advanced Privacy (AAP)

Le cadre de confidentialité avancée agrégée (CAA) d'AppsFlyer empêche à la fois le suivi entre les applications et les sites web appartenant à différentes sociétés et la possibilité d'identifier de manière unique un utilisateur ou un appareil. La CAA prend comme référence les seuils de transparence du suivi d'app (ATT) d'Apple pour définir son niveau de protection de la vie privée.

Le cadre permet aux annonceurs de contrôler la disponibilité des données d'attribution de niveau utilisateur via la plateforme AppsFlyer.

Depuis iOS 14.5 et la mise en place de l'ATT par Apple, si la CAA s'applique, les données d'attribution de niveau utilisateur pour les utilisateurs non consentants sous iOS 14.5 et + ne sont pas disponibles pour les annonceurs ou les partenaires.

La CAA n'affecte pas la disponibilité des données d'attribution agrégées et des rapports analytiques pour les annonceurs et les partenaires.

<div id="aap-impacted-features" />

### Fonctionnalités affectées par la CAA

Si la CAA est activée, les données fournies par les données brutes sont affectées et certains champs sont restreints ou non disponibles. Cela affecte les données fournies par les outils suivants :

* Data Locker
* API Pull de données brutes
* API push
* Page d'exportation du dashboard
* Postbacks envoyés aux réseaux
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/deferred-deep-linking">Obtenir l'API de données de conversion (GCD) dans le cadre de l'API</Anchor> de données de niveau utilisateur côté client.

La disponibilité des données est affectée lorsque la CAA est activée comme suit :

* **Données d'attribution et fraude (Protect360) :** <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">certains champs d'attribution sont restreints ou non disponibles.</Anchor>
* **Données sur les clics, les impressions et les clics bloqués (frauduleux) :** <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#identifier-restriction">les identifiants liés aux utilisateurs et aux appareils</Anchor> ne sont pas disponibles.
* **Deep linking différé** : si vous implémentez le deep linking différé dans les médias payants, utilisez <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">l'API de deep linking unifié (UDL).</Anchor> L'ancienne API, qui utilise GCD, ne peut pas être utilisée avec des utilisateurs sans consentement. Dans le cas d'un média propre, le deep linking différé est pris en charge par GCD et la dernière API de deep linking différée.

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## Principes de disponibilité des données dans le cadre de la CAA

Si la CAA s'applique aux données d'un utilisateur donné, la disponibilité des données dépend du statut ATT de cet utilisateur et de la source média d'origine.

Définitions:

* **Données d'attribution de niveau utilisateur :** les enregistrements de données contenant des identifiants de niveau appareil liés à l'attribution de niveau utilisateur
* **Données d'attribution limitées pour les annonceurs :**

  * Disponible : identifiants au niveau de l'appareil. (L'IDFA est disponible si l'utilisateur a donné son consentement.)
  * Indisponible : données d'attribution  reçues via le lien d'attribution de l'éditeur (par exemple, source média et campagne). <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">Liste des champs restreints et non disponibles pour les annonceurs</Anchor>, autrement dit les sources média restreintes.
* **Données d'attribution limitées pour les partenaires :**

  * Disponible : détails agrégés de la campagne.
  * Non disponible : données de niveau utilisateur permettant d'identifier ce dernier, telles que l'ID AppsFlyer, les données personnalisées, l'ID utilisateur client (CUID), l'ID de clic, l'IDFA, l'IDFV, l'IMEI, l'agent utilisateur et l'adresse IP.

Les termes définis sont utilisés dans la figure et les sections qui suivent pour décrire les données disponibles pour les annonceurs et les partenaires.

<Image align="center" alt="Advanced Privacy Framework - Advertisers (4).png" src="https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png" />

Advanced Privacy se comporte différemment lorsqu'il est utilisé sur le web et que le paramètre af\_media\_type=web ou af\_media\_type=app doit être utilisé. Voir <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">cet article</Anchor> pour en savoir plus.

<div id="paid-and-owned-media-data-availability" />

### Disponibilité des données sur les médias payants et propres

<div id="paid-media" />

<Accordion title="Médias payants">

Les médias payants comprennent les réseaux publicitaires mobile avec des intégrations dans la plate-forme AppsFlyer, avec lesquels les annonceurs mènent des campagnes. 

<div id="paid-media-data-availability-by-att-status" />

#### Disponibilité des données média payantes selon le statut ATT

<table><tbody><tr><th rowspan="2"><p><span>Type de média</span></p></th><th colspan="2"><p><span>Statut ATT</span></p></th><th colspan="2"><p><span>Données disponibles pour :</span></p></th></tr><tr><th><p><span>App d'éditeur</span></p></th><th><p><span>App d'annonceur</span></p></th><th><p><span>Annonceur</span></p></th><th><p><span>Réseau publicitaire</span></p></th></tr><tr><td rowspan="4"><p><span>Téléchargement</span></p></td><td><p><span>Autorisé(e)</span></p></td><td><p><span>Autorisé(e)</span></p></td><td><p><span>Données d'attribution au niveau de l'utilisateur</span></p></td><td><p><span>Données d'attribution au niveau de l'utilisateur</span></p></td></tr><tr><td><p><span>Non autorisé(e)</span></p></td><td><p><span>Autorisé(e)</span></p></td><td><p><span>Données d'attribution limitées pour les annonceurs </span></p></td><td><p><span>Données d'attribution limitées pour les partenaires</span></p></td></tr><tr><td><p><span>Autorisé(e)</span></p></td><td><p><span>Non autorisé(e)</span></p></td><td><p><span>Données d'attribution limitées pour les annonceurs </span></p></td><td><p><span>Données d'attribution limitées pour les partenaires</span></p></td></tr><tr><td><p><span>Non autorisé(e)</span></p></td><td><p><span>Non autorisé(e)</span></p></td><td><p><span>Données d'attribution limitées pour les annonceurs </span></p></td><td><p><span>Données d'attribution limitées pour les partenaires</span></p></td></tr><tr><td rowspan="2"> <br/><p><span>Web</span></p></td><td><p><span>S/O</span></p></td><td><p><span>Autorisé(e)</span></p></td><td><p><span>Données d'attribution au niveau de l'utilisateur</span></p></td><td><p><span>Données d'attribution au niveau de l'utilisateur</span></p></td></tr><tr><td><p><span>S/O</span></p></td><td><p><span>Non autorisé(e)</span></p></td><td><p><span>Données d'attribution limitées pour les annonceurs </span></p></td><td><p><span>Données d'attribution limitées pour les partenaires</span></p></td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Médias propres">

L'infrastructure AppTrackingTransparency d'Apple s'applique uniquement aux données collectées auprès de différentes entreprises. Par conséquent, les données d'attribution de niveau utilisateur des médias sont disponibles pour les annonceurs, quel que soit le statut du consentement ATT de l'utilisateur.

Les médias propres comprennent les campagnes de marketing numérique utilisées par les annonceurs pour atteindre les clients. Il s'agit notamment des campagnes par e-mail, des promotions croisées, des notifications push, etc. Dans AppsFlyer, les campagnes qui utilisent des réseaux publicitaires ne sont pas considérées comme des médias propres.

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## Contrôle du cadre AAP

<div id="aap-central-switch" />

<Accordion title="Niveau de confidentialité avancé agrégé — commutateur au niveau de l'application">

Le CAA est un commutateur au niveau de l'application qui contrôle les paramètres de confidentialité avancés pour tous les partenaires de l'application sélectionnée. Le CAA se trouve sur la page **Paramètres de l'app**. Lorsque le CAA est activé, les commutateurs **Confidentialité avancée** pour tous les partenaires de l'application sélectionnée sont automatiquement activés et ne peuvent pas être modifiés. Lorsque ce commutateur est désactivé, les annonceurs peuvent aller sur le site de chaque partenaire individuellement et activer **Confidentialité avancée**.

<Image align="center" alt="AAPcontrol.png" src="https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png" />

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

<div id="aap-disabled" />

<div id="aap-enabled" />

#### **CAA activée**

* L'attribution agrégée est disponible. Cela inclut par exemple les vues d'ensemble du tableau de bord et les outils de reporting comme Cohort et l'API principale.
* [Les commutateurs de confidentialité avancée du partenaire](/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch) sont activés et ne peuvent pas être modifiés. Attention : ils sont verrouillés.
* La disponibilité des données de niveau utilisateur pour les annonceurs et les partenaires est limitée, comme indiqué dans la [section précédente](/docs/apply-aggregated-advanced-privacy-framework#principes-de-disponibilité-des-données-dans-le-cadre-de-la-caa).

**CAA désactivée**

* L'attribution agrégée est disponible. Cela inclut par exemple les vues d'ensemble du tableau de bord et les outils de reporting comme Cohort et l'API principale.
* Les données d'attribution de niveau utilisateur sont disponibles pour les annonceurs.
* Le paramètre de confidentialité avancée peut être défini individuellement pour chaque partenaire.

*Avant de désactiver la CAA, demandez-vous si cette action va permettre à des tiers d'accéder aux données d'attribution de niveau utilisateur et comment ils vont les utiliser. Vous devez travailler en étroite collaboration avec vos conseillers juridiques et autres professionnels concernant la façon dont Apple définit le suivi. Rien de ce qui est dit ici ne constitue un avis juridique. Ces indications sont purement fournies à titre d'information.*

**Pour définir le paramètre de confidentialité avancée agrégée** :

1. Dans AppsFlyer, allez sur **Réglages** >  **Paramètres de l'app**.
2. Activez ou désactivez l'option **Confidentialité avancée agrégée** si nécessaire.
3. Cliquez sur **Enregistrer**.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Confidentialité avancée — commutateur au niveau du partenaire">

Si la CAA est désactivée, les annonceurs peuvent définir individuellement le paramètre de confidentialité avancée pour chaque réseau publicitaire.

<Image align="center" alt="APControl.png" src="https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png" />

**Pour désactiver la confidentialité avancée d'un partenaire :**

1. Vérifiez que le commutateur central du CAA est désactivé sur la page **Paramètres de l'application**.
2. Allez sur **Configuration** > **Intégrations actives**. Sélectionnez le réseau publicitaire.
3. Dans l'onglet **Intégration**, désactivez la **Confidentialité avancée.**

**Modification du paramètre CAA et impact sur le paramètre de confidentialité avancée du partenaire**

Comme indiqué précédemment, le paramètre CAA remplace le paramètre Confidentialité avancée au niveau du partenaire. Toutefois, si vous désactivez par la suite la CAA (via le commutateur central), les paramètres de confidentialité avancée au niveau des partenaires individuels reviennent à leur état précédent. Cela signifie que :

* Dans le passé, vous avez désactivé la CAA, ainsi que certains paramètres de confidentialité avancée de certains partenaires.
* Plus tard, vous avez réactivé la CAA. N'oubliez pas que lorsque la CAA est activée, elle remplace le réglage du partenaire et tous les partenaires sont considérés comme étant activés.
* Maintenant, vous désactivez à nouveau la CAA. Cela signifie que les paramètres individuels du partenaire s'appliquent. Ainsi, pour certains partenaires, le réglage est déjà désactivé.

</Accordion>

## Implications relatives à la CAA pour vos partenaires

<div id="ad-networks" />

<Accordion title="Réseaux publicitaires">

<div id="postbacks-to-ad-network-partners" />

#### **Postbacks aux partenaires du réseau publicitaire**

<Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks">La CAA affecte les réseaux publicitaires</Anchor> par rapport aux données auxquelles ils ont accès et est conforme aux principes de CAA qui s'appliquent aux annonceurs dans le contexte d'un réseau publicitaire. Les données sont partagées avec les réseaux publicitaires via des postbacks qui diffèrent entre le réseau publicitaire attribué et le réseau publicitaire non attribué.

Les règles de partage des données décrites s'appliquent à un réseau publicitaire donné si l'un des commutateurs suivants est activé :

* AAP : commutateur au niveau de l'application
* AP : commutateur au niveau du partenaire

<div id="postbacks-for-attributed-ad-networks" />

#### **Postbacks pour les réseaux publicitaires attribués**

Dans le cas du réseau attribué, le type de postback utilisé pour partager des données dépend du consentement de l'utilisateur :

* **Utilisateurs ayant donné leur consentement :** postback régulier contenant des données d'attribution de niveau utilisateur, y compris des identifiants.
* **Utilisateurs n'ayant pas donné leur consentement :** postback de confidentialité avancée contenant des données d'attribution limitées. Il contient les détails de la campagne et aucun identifiant.
  * **Condition obligatoire** : pour qu'un réseau publicitaire obtienne des postbacks de confidentialité avancée, une intégration de confidentialité avancée doit exister avec AppsFlyer. Sans intégration, aucun postback n'est envoyé pour les utilisateurs qui n'ont pas donné leur consentement.
  * **Exception :** pour les installations attribuées à Apple Search Ads (ASA), lorsqu'un réseau publicitaire qui ne prend pas en charge la confidentialité avancée règle les postbacks d'installation sur **Toutes les sources média, y compris les sources organiques**, Apple Search Ads (ASA) envoie tout de même les postbacks d'installation au réseau publicitaire, quel que soit le statut de la confidentialité avancée côté annonceur.

Les différents scénarios de consentement de l'utilisateur et les types de postbacks utilisés sont illustrés dans la figure suivante.

<Image align="center" alt="AAP - Attributed ad networks.png" src="https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png" />

Advanced Privacy se comporte différemment lorsqu'il est utilisé sur le web et que le paramètre af\_media\_type=web ou af\_media\_type=app doit être utilisé. Voir <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">cet article</Anchor> pour en savoir plus.

<div id="postbacks-for-unattributed-partners" />

#### **Postbacks pour les partenaires non attribués**

Les postbacks non attribués sont envoyés à un réseau lorsque l'option d'envoi dans l'onglet d'intégration du partenaire intégré est réglée sur *« toutes les sources média, y compris organiques »* et que ce partenaire n'est pas attribué à l'événement, comme l'illustre la figure suivante.

<Image align="center" alt="InAppEventAll.png" src="https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png" />

Les différents scénarios de consentement de l'utilisateur et les types de postbacks utilisés sont illustrés dans la figure suivante.

<Image align="center" alt="AAP - Unattributed ad networks.png" src="https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png" />

Advanced Privacy se comporte différemment lorsqu'il est utilisé sur le web et que le paramètre af\_media\_type=web ou af\_media\_type=app doit être utilisé. Cliquez <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">ici</Anchor> pour obtenir plus d'informations.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Partenaires d'analyse">

La CAA affecte les partenaires d'analyse par rapport aux données auxquelles ils ont accès et est conforme aux principes de CAA qui s'appliquent aux annonceurs dans le contexte du partenaire d'analyse.  Les données partagées avec le partenaire sont envoyées via des postbacks.

Les règles de partage des données décrites s'appliquent à un partenaire donné si l'un des commutateurs suivants est activé :

* AAP : commutateur au niveau de l'application
* AP : commutateur au niveau du partenaire

Les postbacks contenant des données d'attribution de niveau utilisateur, y compris les identifiants d'utilisateur, sont envoyés pour les utilisateurs ayant donné leur consentement. Aucun postback n'est envoyé pour les utilisateurs n'ayant pas donné leur consentement.

Les différents scénarios de consentement de l'utilisateur et les types de postbacks utilisés sont illustrés dans la figure suivante.

<Image align="center" alt="AAP - Analytics partner.png" src="https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png" />

Advanced Privacy se comporte différemment lorsqu'il est utilisé sur le web et que le paramètre af\_media\_type=web ou af\_media\_type=app doit être utilisé. Cliquez <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">ici</Anchor> pour obtenir plus d'informations.

</Accordion>

<div id="agencies" />

<Accordion title="Agences">

**Disponibilité des données** : l'impact de la CAA sur les agences est le même que pour les annonceurs. Si des données brutes sont disponibles pour l'agence pour une app donnée et que la CAA s'applique aux données d'un utilisateur donné, les données sont disponibles conformément aux règles des [données d'attribution limitées pour les annonceurs](/docs/apply-aggregated-advanced-privacy-framework#principes-de-disponibilité-des-données-dans-le-cadre-de-la-caa). 

**Agence modifiant le paramètre de confidentialité avancée d'un réseau publicitaire :**

* Si la CAA est désactivée, il est possible de définir un paramètre de confidentialité avancé pour chaque partenaire.
* Par défaut, seuls les annonceurs peuvent modifier le paramètre de confidentialité avancé. Toutefois, l'annonceur peut explicitement autoriser l'agence à définir le paramètre de confidentialité avancé des réseaux publicitaires activés par celle-ci.

**Accorder à une agence l'autorisation de définir la confidentialité avancée**

<Image align="center" alt="agency_advanced_privacy.png" src="https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png" />

**Pour permettre à une agence de définir la confidentialité avancée** :

1. Allez dans **Configuration** > **Intégrations actives**. Sélectionnez l'agence.
2. Dans l'onglet **Autorisations**, activez **Modifier le paramètre de** **confidentialité avancée.**
3. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Guide de protection de la vie privée et macros de postbacks pour les réseaux publicitaires</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=cadre-aggregated-advanced-privacy-aap h_01HDPDE0H3SYFWBHK59HBV2P6N=cadre-aggregated-advanced-privacy-aap aapimpacted-features=fonctionnalit%C3%A9s-affect%C3%A9es-par-la-caa h_01HDPDE0H339BPACN235V70MWW=fonctionnalit%C3%A9s-affect%C3%A9es-par-la-caa data-availability-principles-in-aggregated-advanced-privacy=principes-de-disponibilit%C3%A9-des-donn%C3%A9es-dans-le-cadre-de-la-caa h_01HDPDE0H3QBE60DVBZ1MWNB9N=principes-de-disponibilit%C3%A9-des-donn%C3%A9es-dans-le-cadre-de-la-caa paid-and-owned-media-data-availability=disponibilit%C3%A9-des-donn%C3%A9es-sur-les-m%C3%A9dias-payants-et-propres h_01HDPDE0H326EXNCQHPVJWXK3H=disponibilit%C3%A9-des-donn%C3%A9es-sur-les-m%C3%A9dias-payants-et-propres h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=disponibilit%C3%A9-des-donn%C3%A9es-m%C3%A9dia-payantes-selon-le-statut-att h_01HDPDE0H3SACYAV19WQD9TCQ3=disponibilit%C3%A9-des-donn%C3%A9es-m%C3%A9dia-payantes-selon-le-statut-att h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=contr%C3%B4le-du-cadre-aap h_01HDPDE0H4VQC2DWAV68Q9VDVQ=contr%C3%B4le-du-cadre-aap h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=caa-activ%C3%A9e h_01HDPDE0H4SC810EBK7ZGQ02K0=caa-activ%C3%A9e h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch aap-implications-for-your-partners=implications-relatives-%C3%A0-la-caa-pour-vos-partenaires h_01HDPDE0H4GJG05FEJP1YM06AP=implications-relatives-%C3%A0-la-caa-pour-vos-partenaires h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=postbacks-aux-partenaires-du-r%C3%A9seau-publicitaire h_01HDPDE0H47ENYTWRVFPX0VTZC=postbacks-aux-partenaires-du-r%C3%A9seau-publicitaire postbacks-for-attributed-ad-networks=postbacks-pour-les-r%C3%A9seaux-publicitaires-attribu%C3%A9s h_01HDPDE0H4B01YG577QZCG7TA7=postbacks-pour-les-r%C3%A9seaux-publicitaires-attribu%C3%A9s postbacks-for-unattributed-partners=postbacks-pour-les-partenaires-non-attribu%C3%A9s h_01HDPDE0H63ZMV255SN7EKDRMV=postbacks-pour-les-partenaires-non-attribu%C3%A9s h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=%C3%A0-consulter-%C3%A9galement" />
