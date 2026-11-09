---
title: Intégration de Medialyzer avec AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2023-09-13T15:02:54Z'
  id: 14963611180689
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/14963611180689
---
> **En bref :** Medialyzer, un partenaire intégré d'AppsFlyer, développe et propose le logiciel comme service. Cette solution permet aux planificateurs de médias d'optimiser leurs campagnes TV visant les entreprises en mettant à profit les visites et conversions générées par les publicités TV diffusées.

<div id="important" />

> 🚧 **Important !**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Certaines sources média</Anchor> limitent le partage de données avec des tiers .Par conséquent, les postbacks des événements limités ne seront pas envoyés à ce partenaire, quelle que soit la sélection configurée pour l'envoi de postbacks.

<div id="setting-up-medialyzer" />

## Configurer Medialyzer

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver le partenaire vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

> 📘 **Remarque**
>
> Avant de configurer une attribution, vous devez <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer l'intégration :**

1. Dans le menu situé en haut de n'importe quelle page AppsFlyer, cliquez sur **Marketplace**.
2. Trouvez le partenaire voulu et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet **Integration** , sélectionnez l'app à intégrer et cochez **Activer le partenaire**.  
   **Remarque :** La case doit rester cochée (option <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

La fenêtre de configuration n'utilise que l'onglet **Integration** .

Pour obtenir une description détaillée de l'en-tête de fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

<div id="activate-partner" />

#### Activation du partenaire

Lors de votre première visite, vous devrez cocher l'option **Activer le partenaire** pour configurer l'intégration. L'option doit rester activée tant que vous travaillez avec Medialyzer. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">l'activation d'un partenaire</Anchor>.

<div id="advanced-privacy" />

#### Protection de la vie privée avancée

Pour les apps iOS, le bouton <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Activer la confidentialité avancée</Anchor> apparaît. Lorsque cette fonction est activée, elle limite le partage des identifiants des utilisateurs avec le partenaire. Notez que lorsque l'option <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée agrégée</Anchor> est activée dans les paramètres de l'app, l'option **Confidentialité avancée (pour iOS 14.5 et +)** est activée et verrouillée par défaut.

<div id="default-postbacks" />

#### Postbacks par défaut

Par défaut, AppsFlyer envoie un postback à Medialyzer après chaque installation par l'utilisateur. Utilisez cette section pour <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#f">définir ces postbacks</Anchor>.

* **Off (désactivé)**: les postbacks d'installation ne sont pas envoyés à Medialyzer.
* **Toutes les sources média, y compris organiques** : envoie un postback d'installation pour tout événement attribué à un partenaire ou tout événement organique.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png" />

<div id="in-app-event-postbacks" />

#### Postback d'évènements in-app

Dans cette section, vous pouvez mapper vos événements AppsFlyer avec vos partenaires via des postbacks.

<Image align="center" alt="app_event_postbacks.JPG" src="https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png" />

1. Activez **Postbacks d'événement in-app.**
2. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
3. Remplissez les paramètres suivants : 

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique puis revérifiez.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Saisissez le nom ou l'ID correspondant à chaque événement (tel que défini dans BPM), ou envoyez les événements tels quels sans mappage du nom. |
| **pour les utilisateurs de** | Sélectionnez **Toutes les sources média, y compris organiques** pour envoyer un postback pour tout événement attribué à un partenaire, ou tout événement organique. |
| **Y compris** | <ul><li>**Sans valeur et sans revenu** : envoyez uniquement l'événement, sans aucun paramètre (valeur ou revenu).</li><li>**Avec valeurs et sans revenu** : envoyez tous les paramètres **à l'exception** de la valeur du revenu.</li><li>**Avec valeurs et avec revenus** : envoyez tous les paramètres de l’événement, **y compris** la valeur du revenu (si incluse dans l’événement).</li></ul> |

4. Cliquez sur **Enregistrer l'intégration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Les liens d'attribution ne sont pas proposés dans Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Les données de coût ne sont pas prises en charge dans l'intégration avec Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas pris en charge dans l'intégration avec Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Les autorisations ne sont pas disponibles dans Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=important- setting-up-spoteffects=configurer-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=configurer-medialyzer h_01H9FKEAV3AV8YMNADQ62476YR=remarque h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=activation-du-partenaire h_01H9FKEAV3DW2A6RQ1NS44FT5F=activation-du-partenaire advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e h_01H9FKEAV3T3YCPBYW70QVF540=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e default-postbacks=postbacks-par-d%C3%A9faut h_01H9FKEAV3Z1Y09P6E18J8AVX2=postbacks-par-d%C3%A9faut inapp-event-postbacks=postback-d%C3%A9v%C3%A8nements-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postback-d%C3%A9v%C3%A8nements-in-app h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
