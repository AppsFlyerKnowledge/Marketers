---
title: Utilisateurs uniques
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-08-11T09:52:33Z'
  edited_at: '2024-08-20T06:43:56Z'
  id: 27435981457553
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/27435981457553
---
> **En bref :** découvrez comment les utilisateurs uniques sont comptabilisés et utilisés dans les résultats des tableaux de bord et rapports AppsFlyer.

## À propos des utilisateurs uniques

Un utilisateur unique fait référence à un appareil attribué dont la présence n'est comptabilisée qu'une seule fois, quel que soit le nombre d'actions qu'un utilisateur effectue sur l'appareil.

Il s'agit d'un chiffre utilisé dans beaucoup de mesures marketing différentes, notamment :

* Installations : le nombre d'utilisateurs uniques à avoir téléchargé et installé l'application.
* Taux de rétention : le pourcentage d'utilisateurs uniques avec une session au cours de la journée.
* Utilisateurs uniques de l'événement : le nombre d'utilisateurs uniques (attributions) à avoir réalisé l'événement.
* Utilisateurs actifs quotidiens (DAU) : le nombre d'utilisateurs uniques (comptabilisés une seule fois) qui ont ouvert l'app au moins une fois dans la journée.
* Liste non exhaustive...

Le calcul des utilisateurs uniques est basé sur l'ID de l'appareil (comme l’IDFA ou le GAID). Si aucun ID d'appareil n'est disponible (comme pour iOS SKAN), l'ID AppsFlyer est utilisé à la place. Ainsi, l’utilisateur ne peut être comptabilisé qu’une seule fois puisque l'ID d’appareil ou l'ID AppsFlyer est le même pour toutes les actions, et ce quel que soit le nombre de sessions ou d'actions effectuées.

## Cas d’utilisation

Bien que le calcul de l'utilisateur unique soit généralement simple, des questions peuvent surgir concernant certains comportements ou actions de l'utilisateur. Les cas d’utilisation suivants vous expliquent comment les utilisateurs uniques sont comptés dans certains cas plus complexes.

<div id="install-and-reinstall" />

<Accordion title="Installation et réinstallation">

![](https://files.readme.io/8b9f3c442f98c056069b4449c7e5115cbea828a64ace3a98e0090fb0d8d1d8d6-27455116159889.png)

L'installation et la réinstallation ont le même ID d'appareil/ID AppsFlyer. Par conséquent, 1 utilisateur unique sera comptabilisé. Les deux événements in-app sont attribués au même utilisateur unique que celui de la première installation.

**Remarque** :

* Si une réinstallation n'inclut pas d'ID d'appareil/ID AppsFlyer, elle ne peut pas être reliée à la première installation et est considérée comme « organique non attribuée ». Les événements post-réinstallation résultants de réinstallations organiques non attribuées ne sont pas comptés dans le nombre d'utilisateurs uniques.
* Il peut y avoir d’autres raisons qui font qu’un événement n’est pas attribué de manière organique. Dans ces cas également, les événements ne sont pas compris dans le nombre d’utilisateurs uniques.

</Accordion>

<div id="install-and-reattribution" />

<Accordion title="Installation et réattribution">

![](https://files.readme.io/40420c5ea201ba7cf13d03e5968d20c2fffaa31b74c47ae36cd917cccbaae353-27453973190289.png)

L'installation et la réattribution ont le même ID d'appareil/ID AppsFlyer. Mais dans ce cas précis, AppsFlyer prend aussi en compte le paramètre `is_retargeting=true`, l'événement post- réattribution est donc comptabilisé comme un utilisateur unique supplémentaire. Au final, 2 utilisateurs uniques sont comptabilisés.

* Dans le tableau de bord Général, la vue UA affiche 1 utilisateur unique, et ce car les réattributions de retargeting ne sont pas affichées dans la vue UA. C’est la même chose pour les rapports UA.
* Dans le tableau de bord Général, la vue de retargeting affiche 1 utilisateur unique, et ce car les installations UA ne sont pas affichées dans la vue de retargeting. Même chose pour les rapports de retargeting.
* Dans le tableau de bord Général, la vue unifiée affiche 2 utilisateurs uniques : 1 relié à la première installation et le 2ème relié à la réattribution. Même chose pour les rapports unifiés.

</Accordion>

<div id="install-and-reengagement" />

<Accordion title="Installation et réengagement">

![](https://files.readme.io/04adbd0d79f5999ca1c39f49f4e0469571c80f1be7918e9e2d8617a0ae8abccf-27458250919441.png)

L'installation et le ré-engagement ont le même ID d'appareil/ID AppsFlyer. Mais dans ce cas précis (comme pour les réattributions), AppsFlyer prend aussi en compte le paramètre `is_retargeting=true`, l'événement qui se produit après le ré-engagement est donc comptabilisé comme un utilisateur unique supplémentaire. Au final, 2 utilisateurs uniques sont comptabilisés.

* Dans le tableau de bord Général, la vue UA affiche 1 utilisateur unique, et ce car les ré-engagements de retargeting ne sont pas affichées dans la vue UA. C’est la même chose pour les rapports UA.
* Dans le tableau de bord Général, la vue de retargeting affiche 1 utilisateur unique, et ce car les installations UA ne sont pas affichées dans la vue de retargeting. Même chose pour les rapports de retargeting.
* Dans le tableau de bord Général, la vue unifiée affiche 2 utilisateurs uniques : 1 relié à la première installation et le 2ème relié au ré-engagement. Même chose pour les rapports unifiés.

</Accordion>

<div id="unattributed-inapp-events" />

<Accordion title="Événements in-app non attribués">

![](https://files.readme.io/94bf078bcf4ba26a1dc4ca323a1b4a7543cfb4e3fc8b780d0d29713c4266aa95-27455116170001.png)

Lorsqu'un événement in-app n'est pas attribué (il suit une réinstallation, pour une raison quelconque, il n'est pas lié à la première installation), il n'est pas pris en compte dans le nombre d'utilisateurs uniques. Cela peut se produire lorsqu'aucun ID d'appareil n'est disponible pour la réinstallation, mais ce n’est pas forcément la seule explication. <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#unattributed-organic-inapps">En savoir plus</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Détails |
| --- | --- |
| Événement de revenus publicitaires<br /><br />(af\_ad revenue) | <ul><li>Le nombre d'utilisateurs uniques est pris en charge pour les événements de revenus publicitaires dans les cas suivants :<ul><li>Mesures de cohorte sur la journée</li><li>Mesures d'activité</li><li>Mesures SKAN</li></ul></li><li>Le nombre d'utilisateurs uniques n'est pas pris en charge pour les événements de revenus publicitaires dans les cas suivants :<ul><li>Mesures cumulatives de cohorte</li><li>Mesures LTV via la méthode d'attribution classique **Remarque** : en d’autres termes, cela signifie que lorsque vous consultez un tableau de bord en vue SSOT, la mesure des utilisateurs uniques pour les événements de revenus publicitaires est disponible pour les données SKAN, mais pas pour les données d'attribution classiques.</li></ul></li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=%C3%A0-propos-des-utilisateurs-uniques 01H7Z1003GTTMRY072BXWDFNP0=%C3%A0-propos-des-utilisateurs-uniques use-cases=cas-dutilisation h_01J52T4MT63JVJEQ050E2BXMVQ=cas-dutilisation h_01J52T9B4ZZH1TBW98YM5MY675=install-and-reinstall h_01J52T9B4ZYWQAGS3QHG99G3AS=install-and-reattribution h_01J531V2AKW8QP33B6K8QFH72R=install-and-reengagement h_01J52WPCZEBFP4RR0Y4ZC5TABK=unattributed-inapp-events h_01J52ZHXKYDG77PE70QZV63KY3=traits-and-limitations" />
