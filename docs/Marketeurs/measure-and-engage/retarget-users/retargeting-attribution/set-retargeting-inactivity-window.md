---
title: Période d'inactivité du retargeting
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2024-08-21T13:09:06Z'
  id: 360009305817
  locale: fr
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/fr/articles/360009305817
---
> **En bref :** augmentez le saut incrémentiel en reciblant les utilisateurs inactifs, définissez les fenêtres d'inactivité par source média.
>
> ![](https://files.readme.io/f55130956ae4fcb32fff4f0590fc942f3d3c024bc09de99968e1f29933ceb26b-9479865167761.png)

## Période d'inactivité

Les annonceurs retrouvent les utilisateurs inactifs en les reciblant. Ces campagnes ont généralement un bon taux de conversion et génèrent un ROAS significatif. Cependant, de nombreuses campagnes de retargeting sont moins performantes car elles ne filtrent pas les utilisateurs actifs. Pour augmenter le saut incrémentiel des campagnes de retargeting, mettez en place un **temps d'inactivité minimum** pour filtrer les utilisateurs actifs.

En fixant une durée d'inactivité minimum, les annonceurs n'attribuent pas les utilisateurs actifs. Par exemple, si la période d'inactivité minimale est de trois jours, les utilisateurs actifs au cours des 0 à 3 jours précédents ne sont pas attribués. Les utilisateurs inactifs pendant quatre jours ou plus sont attribués. La période d'inactivité s'applique à la fois aux cas de réattribution et de réengagement. En cas de réattribution, la dernière activité est la dernière session avant la désinstallation.

**Règles d'inactivité**

* **Attribué :** les utilisateurs inactifs qui n'ont pas utilisé l'application pendant une durée plus longue que celle de la période d'inactivité définie. Les réengagements et les réinstallations de retargeting sont attribués.
* **Non attribué** : les utilisateurs actifs qui ouvrent l'application mais ne dépassent pas la période minimale d'inactivité ne sont pas pris en compte et ne sont pas attribués à la campagne de retargeting.

### Terminologie de l'inactivité de retargeting

| Terme | Définition |
| --- | --- |
| Valeur maxi | 30 jours |
| Valeur par défaut | 0 (aucun)  <br />La fonctionnalité **Période d'inactivité** n'est pas active par défaut pour les sources média. |
| Activité de l'utilisateur | Installations ou sessions rapportées via SDK ou S2S. |
| Appareils migrés | L'heure de la migration correspond à l'heure de la dernière activité. |

## Scénarios

Dans les scénarios de retargeting suivants, la période d'inactivité est définie pour la source média.

<div id="reattribution" />

<Accordion title="Réattribution">

Les actions de l’utilisateur sont les suivantes : L'utilisateur :

* désinstalle l'application puis reste inactif
* participe à une campagne de retargeting menée par une source média
* réinstalle l'application

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| Scénario | Seuil d'inactivité | Période d'inactivité de l'utilisateur | Résultat |
| --- | --- | --- | --- |
| A | 7 jours | 8 jours<br /><br />**L'utilisateur est resté inactif** pendant une période plus longue que le seuil d'inactivité | <ul><li>**Réattribution** (retargeting, réinstallation)</li><li>Attribué à la source média de retargeting A</li></ul> |
| B | 14 jours | 5 jours<br /><br />L'utilisateur était actif. | <ul><li>**Réinstallations organiques**</li><li>**Réinstallation non organique :** si l'utilisateur a utilisé une source média UA.</li><li>La source média de retargeting A ne peut pas être attribuée en raison du seuil d'inactivité de l'utilisateur.</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="Ré-engagement">

Les actions de l’utilisateur sont les suivantes : L'utilisateur :

* installe l'app
* reste inactif pendant plusieurs jours
* suit une campagne de retargeting, menée par une source média, puis lance l'application

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| Scénario | Seuil d'inactivité de la source média A | Période d'inactivité de l'utilisateur | Résultat |
| --- | --- | --- | --- |
| A | 7 jours | 8 jours<br /><br />**L'utilisateur est resté inactif** pendant une période plus longue que le seuil d'inactivité | <ul><li>**Réengagement** attribué à la source média A</li></ul> |
| B | 7 jours | 4 jours<br /><br />**L'utilisateur a utilisé l'application** pendant la période d'inactivité définie. | <ul><li>**Session classique**</li><li>La source média de retargeting A n'est pas attribuée</li></ul> |

</Accordion>

## Configuration du partenaire

<div id="zd-srn" />

<Accordion title="SRN">

Cette fonctionnalité est configurée dans l'onglet Intégration des SRN qui prennent en charge les périodes d'inactivité.

**Pour définir une période d'inactivité pour les réseaux self-reporting (SRN) qui prennent en charge le retargeting :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez un SRN.
3. Dans l'onglet **Intégration**, faites défiler vers le bas. Activez **Ignorer l'utilisateur actif pour le retargeting**
4. Définissez la **fenêtre d'inactivité.** (1-30 jours)
5. Cliquez sur **Enregistrer l'intégration**.

[![Inactivity_window_SRN.png](https://files.readme.io/9390ebcab781c6203dd8137183a20284f3d0943d33e609e00a3902a5ef14d848-9479906225553.png)](https://files.readme.io/9390ebcab781c6203dd8137183a20284f3d0943d33e609e00a3902a5ef14d848-9479906225553.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="Non-SRN (réseaux publicitaires de clic)">

**Pour définir une période d'inactivité pour les non-SRN qui prennent en charge le retargeting :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez un réseau publicitaire.
3. Ouvrez l'onglet **Lien d'attribution**, faites défiler vers le bas et activez **Ignorer l'utilisateur actif pour le retargeting**.
4. Définissez la **fenêtre d'inactivité.** (1-30 jours)  
   Le paramètre **Période d'inactivité** `af_inactivity_window` est ajouté au lien d'attribution, exemple : « &af\_inactivity\_window=7d ». Si la fonctionnalité est désactivée, elle ne figure pas dans le lien d'attribution.

[![Inactivity_window_non-SRN.png](https://files.readme.io/36ca6b8903ac80b6bc7bab1dc84ab5d046d0d86a5d3a6fee3cd47da7e3c6d3fb-9479958030353.png)](https://files.readme.io/36ca6b8903ac80b6bc7bab1dc84ab5d046d0d86a5d3a6fee3cd47da7e3c6d3fb-9479958030353.png)

</Accordion>

<div id="agencies" />

<Accordion title="Agences">

#### SRN

Agence (autorisation accordée par l'annonceur)

**Pour accéder à la configuration de la période d'inactivité :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez un SRN.
3. Dans l'onglet **Intégration**, réglez les paramètres comme indiqué dans le tableau suivant.

| SRN | Agence |
| --- | --- |
| DoubleClick | <ul><li>Activer/désactiver le retargeting</li><li>Configurer une période d'inactivité</li></ul> |
| Google Ads | <ul><li>Impossible d'activer/désactiver le retargeting</li><li>Si une agence a les autorisations, elle peut configurer une période d'inactivité</li></ul> |
| Meta ads / X Ads / Snapchat | Ne peut pas accéder au retargeting et à la configuration de la période d'**inactivité** |

#### Non SRN

Partenaire (prend en charge le retargeting)

**Pour définir une période d'inactivité pour les non-SRN qui prennent en charge le retargeting :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez un réseau publicitaire non SRN > Ouvrez l’onglet **Lien d'attribution**.

</Accordion>

<div data-zendesk-anchors="inactivity-period=p%C3%A9riode-dinactivit%C3%A9 h_01H9JS3QKW5S7VP9YW05CB6STR=p%C3%A9riode-dinactivit%C3%A9 retargeting-inactivity-terminology=terminologie-de-linactivit%C3%A9-de-retargeting h_01H9JS3QKXMBS95RG06A9JXGT0=terminologie-de-linactivit%C3%A9-de-retargeting scenarios=sc%C3%A9narios h_01H9JS3QKXWDX8Y58GX1G5HNYY=sc%C3%A9narios h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=configuration-du-partenaire h_01H9JS3QKXGNFM8499G52458B2=configuration-du-partenaire srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=non-srn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=non-srn" />
