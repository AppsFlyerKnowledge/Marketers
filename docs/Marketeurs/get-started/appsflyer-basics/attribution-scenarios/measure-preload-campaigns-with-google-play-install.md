---
title: Attribution des préchargements via Google Play Auto Install
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2024-08-26T13:17:49Z'
  id: 4404557237649
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/4404557237649
---
> **En bref :** AppsFlyer utilise Google Play Auto Install (PAI) pour attribuer les installations à des campagnes de préchargement, où les marketeurs s’engagent auprès des opérateurs mobile et partenaires de découverte d'apps pour précharger leur app au moment où l'appareil est allumé pour la première fois par l'utilisateur. **Remarque** : Cette méthode d'attribution diffère de l'<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-factory-preinstall-using-manifest-android">attribution de la préinstallation APK.</Anchor>

<div id="pai-preload-attribution" />

## Attribution des préchargements via PAI

Dans les campagnes de préchargement, les fabricants d'appareils d'origine (OEM), les opérateurs de téléphonie mobile et partenaires de découverte d'app, préchargent des applications qui sont téléchargées lors de la première activation de l'appareil.

Les campagnes de préchargement permettent aux annonceurs d'atteindre un plus large public sans avoir à lancer de campagnes en ligne.

Google Play Auto Install (PAI) (1 des 3 méthodes d'attribution de préchargement) offre aux marketeurs un moyen précis et respectueux de la vie privée pour mesurer les performances des campagnes de préchargement. Cette méthode offre aux marketeurs des résultats d'attribution déterministes, et elle garantit le respect de la confidentialité puisque l'attribution est effectuée en associant le référent à un référent généré indépendamment de l'ID de l'appareil et de l'utilisateur.

AppsFlyer donne la priorité à l'attribution des préchargements. Cela signifie que si un utilisateur suit d'autres campagnes avant d'ouvrir l'app pour la première fois, la campagne de préchargement est celle qui hérite de l’attribution. Les autres engagements sont considérés comme des installations assistées.

**Remarque** : Les agences ne peuvent pas activer les campagnes de préchargement pour leurs clients.

<div id="flow" />

### Procédé

1. Un nouvel appareil est activé pour la première fois et des applications prédéfinies y sont automatiquement installées depuis Google Play, conformément aux règles établies par le partenaire de préchargement.
2. L'utilisateur lance pour la première fois une application préchargée.
3. Le SDK AppsFlyer interroge l'API du référent de Google Play.
4. AppsFlyer effectue l’attribution en fonction des données reçues.

![PAI-attribution-flow_en-us.png](https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png)

<div id="data-availability" />

### Disponibilité des données

Les données de performance de préchargement de Google Play Auto Install (PAI) sont disponibles dans :

* Le tableau de bord général et les rapports agrégés, regroupés selon le partenaire de préchargement (source média) et la campagne.
* Les rapports de données brutes.

Les données brutes incluent les champs suivants :

* Media\_source = Partner ID
* Match\_type = preload\_pai
* Campaign\_name = campagne de préchargement par `<preloadpartner ID>`

<div id="set-up-google-play-auto-install-pai-preload-attribution" />

### Configurer l'attribution de préchargement de Google Play Auto Install (PAI)

**Pour configurer l'attribution de préchargement de PAI :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez le partenaire de préchargement.
3. Activer l'**attribution de préchargement.**
4. Définissez la longueur de la **fenêtre rétrospective de préchargement.** Période : 1-180 jours
5. Cliquez sur **Enregistrer l'intégration**.
6. Informez le partenaire de préchargement que vous êtes en capacité d'attribuer ses campagnes.

<div id="partners-supporting-google-play-auto-install-pai-preload-campaigns" />

### Partenaires prenant en charge les campagnes de préchargement Google Play Auto Install (PAI)

<table><thead><tr><th rowspan="2">Partenaire</th><th rowspan="2">PID</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>KDDI Pre-Install</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

<div id="postbacks-for-preload-partners" />

## Postbacks pour les partenaires de préchargement

Dans le cadre de leur intégration avec AppsFlyer, les partenaires de préchargement définissent le contenu et les points de terminaison des postbacks qui leur sont envoyés par AppsFlyer.

Lorsqu'elles sont incluses dans un postback, les macros contiennent des données sur l'utilisateur. Les macros prises en charge sont listées dans le tableau suivant :

* **Source** : Indique l'origine des données :
  * **SDK** : SDK AppsFlyer intégré dans l'app ou l'API de serveur à serveur.
  * **AppsFlyer** : Après traitement par AppsFlyer.

| Macro de postback pour les partenaires de préchargement (nom du paramètre) | Source | Description |
| --- | --- | --- |
| app\_name | SDK | Nom de l'app défini par l'annonceur |
| country\_code | AppsFlyer | Code pays selon la norme ISO 3166 (alpha-2) Exemple : US, CN. |
| install\_time | SDK | Horodateur de l'installation |
| langue | SDK | Langue (locale) transmise par l'appareil et définie par l'OS de l'appareil. |
| app\_id | SDK | Identifiant d'app unique propre à Appsflyer |
| app\_version | SDK | Version de l'app définie par le développeur de l'app dans le code de l'application |
| device\_type | SDK | Le nom du modèle commercial de l'appareil. Ex. SM-GM284 ou iPhone7 |
| os\_version | SDK | Version du système d'exploitation de l'appareil |

<div id="postback-example" />

#### Exemple de postback

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=attribution-des-pr%C3%A9chargements-via-pai h_01HEJG4FHSGJDZ77Y281F7SG4R=attribution-des-pr%C3%A9chargements-via-pai pai-preload-attribution-flow=proc%C3%A9d%C3%A9 h_01HEJG4FHSF8X1TEMMNJBYP71Z=proc%C3%A9d%C3%A9 campaign-performance-data-availability=disponibilit%C3%A9-des-donn%C3%A9es h_01HEJG4FHSCMPJM5TRNSPNDHVN=disponibilit%C3%A9-des-donn%C3%A9es run-preload-referrer-campaigns=configurer-lattribution-de-pr%C3%A9chargement-de-google-play-auto-install-pai h_01HEJG4FHS7E5JZT2BBYG2BNEK=configurer-lattribution-de-pr%C3%A9chargement-de-google-play-auto-install-pai partners-supporting-preload-referrer-campaigns=partenaires-prenant-en-charge-les-campagnes-de-pr%C3%A9chargement-google-play-auto-install-pai h_01HEJG4FHSNEGR7R9VCSDT9TSZ=partenaires-prenant-en-charge-les-campagnes-de-pr%C3%A9chargement-google-play-auto-install-pai postbacks-for-preload-partners=postbacks-pour-les-partenaires-de-pr%C3%A9chargement h_01HEJG4FHSKD7DY6W7W65YBMGN=postbacks-pour-les-partenaires-de-pr%C3%A9chargement preload-postback-example=exemple-de-postback h_01HEJG4FHSBFB456Z752HFC8KN=exemple-de-postback" />
