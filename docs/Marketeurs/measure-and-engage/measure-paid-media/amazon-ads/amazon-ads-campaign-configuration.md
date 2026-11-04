---
title: Configurer une campagne Amazon DSP
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2023-10-27T11:12:32Z'
  id: 11904659502737
  locale: fr
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/fr/articles/11904659502737
---
> **En bref :** Amazon DSP (amazondsp\_int), partenaire intégré d'AppsFlyer, permet aux propriétaires d'app de mesurer via AppsFlyer l'attribution basée sur les clics et les vues avec pour la TV, les tablettes et appareils mobile.

![mceclip0.png](https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png)

<div id="activate-partner" />

## Activation du partenaire

**Condition préalable :** avant de configurer l'intégration, assurez-vous de <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et d'ouvrir un compte chez lui.

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver le nouveau partenaire vous devez d'abord vous rendre dans le marketplace, cf ci-dessous :

**Pour activer l'intégration des partenaires :**

1. Dans AppsFlyer, allez dans **Configuration** > **Marketplace des partenaires.**
2. Repérez l'intégration du nouveau partenaire et sélectionnez-la.
3. Cliquez sur **Configurer l'intégration**. Vous êtes dirigé vers la page de configuration des **Intégrations actives** .
4. Dans l'**onglet Intégration**, cochez **Activer le partenaire**.  
   **Remarque :** La case doit rester cochée (option <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

<div id="setting-up-amazon-ads" />

## Configurer l'intégration Amazon DSP

L'intégration avec Amazon DSP permet l'attribution des clics et impressions. La fenêtre de configuration comprend les onglets suivants : *Intégration*, *Lien d'attribution*, *Coût*, *Revenus publicitaires *et* Autorisations.* Les onglets disponibles dans Amazon DSP sont *Intégration* et *Autorisations*.

<div id="note" />

> 📘 **Remarque**
>
> * Certains paramètres diffèrent entre les appareils iOS et Android
> * En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">la configuration des intégrations de partenaires</Anchor>

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet **Integration** comprend un certain nombre de sections, décrites ci-dessous.

<div id="activate-partner-1" />

#### Activation du partenaire

Pour configurer l'intégration, vous devez d'abord [enclencher](/docs/amazon-ads-campaign-configuration#activation-du-partenaire) la fonction **Activer le partenaire**. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#activating-a-partner">l'activation et la désactivation des intégrations des partenaires.</Anchor>

#### Protection de la vie privée avancée

Pour les applications iOS uniquement : votre contrôle des données partagées avec le partenaire via les postbacks et les <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend de l'état de la fonction **Confidentialité avancée (pour iOS 14.5 et +)** :

| Confidentialité avancée : ON | Confidentialité avancée : OFF |
| --- | --- |
| Les postbacks sont envoyés uniquement pour les événements attribués au partenaire. | Les postbacks sont envoyés selon votre configuration :<ul><li>**Toutes les sources média, y compris organiques**</li><li>**Ce partenaire uniquement**</li></ul> |
| Les postbacks sont envoyés selon le <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks">modèle de confidentialité avancée</Anchor> |  |
| <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Les données agrégées et anonymes</Anchor> sont partagées avec le partenaire, ce qui signifie qu'aucune donnée de niveau utilisateur (identifiant de l'appareil) n'est partagée. |  |

<div id="general-settings" />

#### Paramètres généraux

**ID de produit Amazon**

Il s'agit d'une clé unique générée par le gestionnaire de compte Amazon et fournie à l'annonceur pour les applications Amazon DSP. L'ID de produit Amazon est nécessaire pour compléter l'intégration et permettre l'attribution à Amazon DSP.

#### Postbacks par défaut

Configurez l'envoi de postbacks pour les installations :

* **Ce partenaire uniquement** : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui l'effectue provient de ce partenaire.
* **Toutes les sources média, y compris organiques** : envoi de postbacks pour les événements attribués à n'importe quel partenaire ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média).

> 📘 **Remarque**
>
> * Pour les apps IOS uniquement : la manière dont vous pouvez gérer les données envoyées au partenaire via les postbacks et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend si la **Confidentialité avancée (pour IOS 14.5 et +)** est <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup#protection-de-la-vie-privée-avancée">activée ou non.</Anchor>
> * Les postbacks sont partagés via Data Locker dans un rapport horaire, et non en temps réel.

<div id="install-attribution" />

#### Attribution d'installation

Définir les fenêtres d'attribution post-clic et post-vue pour les installations (premiers lancements). Notez que seules les installations réalisées dans la fenêtre rétrospective peuvent être attribuées à Amazon DSP.

1. Définissez la **Fenêtre rétrospective post-clic d'installation** sur 1-23 heures ou 1-30 jours.  
   **Remarque :** Amazon DSP recommande de régler la fenêtre rétrospective post-clic sur 14 jours, afin de vous aligner sur leur fenêtre d'attribution.
2. [Facultatif] Activez l'option **Attribution des installations post vue** et réglez la **fenêtre rétrospective post-vue d'installation** entre 1 et 24 heures.

<div id="in-app-event-postbacks" />

#### Postback d'évènements in-app

Configurer le mappage des événements in-app avec les événements Amazon DSP qui sont envoyés via postback.

> 📘 **Remarque**
>
> Les postbacks sont partagés via Data Locker dans un rapport horaire, et non en temps réel.

**Pour configurer les postbacks d'événement in-app :**

1. Activez **Postbacks d'événement in-app.**
2. Cliquez sur **Ajouter un événement** pour ajouter un SDK ou événement de serveur à serveur à la liste. Le tableau suivant explique les champs à remplir :  

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique avant de vérifier à nouveau.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks uniquement dans le cas où cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, y compris organiques** : envoie des postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement en lui-même mais sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur de revenu (si présente dans l’événement).</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

3. [Facultatif] Cliquez sur l'icône **Ajouter une condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e3b4e42933325fc5e93d4cc9e892a1b28388648078fddb965a31c8ec8c04b25f-17912947736465.png" width="30px" /> pour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'un événement.
4. Cliquez sur **Enregistrer l'intégration**.
5. [Facultatif] Après avoir enregistré l'intégration, si vous restez sur la page de configuration vous pouvez intégrer d'autres apps à votre partenaire :
   1. Dans le coin en haut à gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
   2. Sélectionnez une autre app dans la liste déroulante.
   3. Répétez les différentes [étapes d’intégration](/docs/amazon-ads-campaign-configuration#integration-tab) pour l’app sélectionnée.

> 📘 **Remarque**
>
> Pour les apps IOS uniquement : la manière dont vous pouvez gérer les données envoyées au partenaire via les postbacks et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend si la **Confidentialité avancée (pour IOS 14.5 et +)** est <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup#protection-de-la-vie-privée-avancée">activée ou non.</Anchor>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Les liens d'attribution ne concernent pas Amazon DSP. L'attribution s'effectue en combinant les données d'engagement issues d'Amazon DSP avec les données d'AppsFlyer, et ce d'après les fenêtres rétrospectives post-vue que vous avez définies dans l'onglet [Intégration.](/docs/amazon-ads-campaign-configuration#integration-tab)

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Les données de coûts ne sont pas disponibles avec Amazon DSP.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas disponibles avec Amazon DSP.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Sélectionnez les autorisations données à Amazon DSP pour accéder à vos données et effectuer diverses actions.

<div id="note-3" />

> 📘 **Remarque**
>
> * Lorsque l'intégration est <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">désactivée</Anchor>, les autorisations sont toujours accordées même si l'option Autorisations est activée.
> * En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations</Anchor> à une agence.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/setting-up-amazon-fire-tv-ad-attribution">Configurer l'attribution des publicités sur Amazon Fire TV</Anchor>

<div data-zendesk-anchors="activate-partner=activation-du-partenaire 01H88VAJH3B5ESK12D3ATMMVZ8=activation-du-partenaire setting-up-amazon-dsp-integration=configurer-lint%C3%A9gration-amazon-dsp 01H88VAJH3VENKYVRQY5RXN63P=configurer-lint%C3%A9gration-amazon-dsp 01H88VAJH3BYZSXQGGZZJQ9N0C=remarque 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activation-du-partenaire-1 01H88VAJH34GP7FK1KTJGRDPM7=activation-du-partenaire-1 advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e 01H88VAJH3G5FAR7RRNDEPNGME=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H88VAJH3F2FJK5YP3M2V7RWD=param%C3%A8tres-g%C3%A9n%C3%A9raux default-postbacks=postbacks-par-d%C3%A9faut 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-par-d%C3%A9faut 01H88VAJH3AETJZGYMY1YK7FJ6=remarque-3 install-attribution=attribution-dinstallation 01H88VAJH3SSG6ZNV7XQ46W5CX=attribution-dinstallation inapp-event-postbacks=postback-d%C3%A9v%C3%A8nements-in-app 01H88VAJH3AS37MVF75GANWX4B=postback-d%C3%A9v%C3%A8nements-in-app h_01HCW04WHZ8HGHBHV4733CS615=remarque-2 01H88VAJH36MYZ9W1YPWA92Z1Z=remarque-3 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=remarque-4 h_01HDNZ59NQEDFC3D8JYGENR1NR=%C3%A0-consulter-%C3%A9galement" />
