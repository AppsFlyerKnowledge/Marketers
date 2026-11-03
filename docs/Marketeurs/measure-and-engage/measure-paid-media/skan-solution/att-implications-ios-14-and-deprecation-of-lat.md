---
title: Implications d'ATT (iOS 14+) et disparition de LAT
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2024-10-06T08:05:28Z'
  id: 360014090597
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/360014090597
---
> **En bref** : À partir d'iOS 14, iOS utilise ATT pour déterminer les préférences de confidentialité des utilisateurs et le suivi de publicités limité (LAT) est obsolète.

### Valeurs ATT

* À partir d'iOS 14 : Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> (ATT) fournit les valeurs d'état pour l'autorisation de suivi des applications.
* AppsFlyer obtient ATT à partir des sources suivantes :
  * SDK AppsFlyer V6+ intégré à l'application.
  * Par API des annonceurs. Par exemple, l'API S2S.
* ATT est disponible dans les rapports de données brutes. Vous devez le demander explicitement comme suit :
  * API Pull : Ajoutez ATT *au paramètre* additional\_fields dans vos requêtes API Pull.
  * Page d'exportation de données : Dans l'onglet des champs du rapport, sélectionnez explicitement ATT.
  * Data Locker : Dans la page de configuration de Data Locker, ajoutez explicitement ATT à la liste des champs.
  * API Push : Dans la page d'accès API, ajoutez explicitement ATT à la liste des champs.
* Dans certains cas, ATT est renseigné par des valeurs définies par AppsFlyer. Elles sont indiquées par le préfixe *af* dans le tableau.
* Si l'IDFA n'est pas disponible, il est renseigné avec des zéros.

#### Valeurs ATT définies par Apple

| Statut ATT | Disponibilité de l'IDFA | Comportement |
| --- | --- | --- |
| non\_déterminé | Dans iOS 14-14.4 : Disponible<br /><br />À partir d'iOS 14.5 : Non disponible | Valeur par défaut d'ATT |
| limité | Pas disponible | Ceci est déterminé par Apple en fonction du compte iTunes et n'est pas lié au comportement de l'utilisateur. Par exemple, en fonction de l'âge de l'utilisateur ou d'appareils contrôlés par des organisations. |
| refusé | Pas disponible | Se produit si l'une des conditions suivantes est vraie :<ul><li>Défini après l'affichage de l'invitation</li><li>L'utilisateur a désactivé *Autoriser les applications à demander le suivi* (commutateur principal au niveau de l'appareil)</li><li>Avant d'installer iOS 14 sur l'appareil, LAT était activé</li></ul> |
| autorisé | Disponible | L'utilisateur a explicitement donné son consentement. |

#### Valeurs ATT supplémentaires définies par AppsFlyer

| Statut ATT | Remarque | Disponibilité de l'IDFA |
| --- | --- | --- |
| af\_inconnu | La valeur ATT a été signalée par l'annonceur mais n'est pas une valeur connue selon la spécification <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> | Dépend de la version iOS |
| af\_autorisé | L'utilisation de l'IDFA est autorisée pour l'une des raisons suivantes:<ul><li>Version iOS de l'appareil: antérieure à iOS 14.</li><li>L'événement signalé contenait l'IDFA mais pas l'ATT. Par exemple, une application avec le SDK V5.X sur un appareil ayant une version iOS antérieure à iOS 14.</li></ul> | Disponible |
| af\_indisponible | <ul><li>L'ATT n'a pas été signalé lors de l'événement par l'annonceur, et l'IDFA n'est pas disponible.</li><li>La version V5.X du SDK AppsFlyer ne peut pas obtenir l'ATT et n'a pas obtenu l'IDFA.</li></ul> | Pas disponible |

### LAT dans iOS – considérations et comment LAT se traduit en ATT dans iOS 14

| Version iOS | Utilisation de LAT |
| --- | --- |
| Jusqu'à iOS 13 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />Si cette option est activée, le suivi limité des publicités par l'utilisateur (LAT) rend l'IDFA indisponible. |
| À partir d'iOS 14 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">Apple a déprécié I*s LAT*</Anchor>. Ne tenez pas compte de la valeur *Is LAT* et utilisez à la place l'ATT. |

**Comment LAT se traduit par ATT dans iOS 14**

[altLATtoiOS14.5.pngalt](https://support.appsflyer.com/hc/article_attachments/360017977837)

<div data-zendesk-anchors="att-values=valeurs-att h_01HGX9468F5YF0KSHB3S49CW2Y=valeurs-att att-values-defined-by-apple=valeurs-att-d%C3%A9finies-par-apple h_01HGX9468F0TFTMKP1W2J6GEBV=valeurs-att-d%C3%A9finies-par-apple additional-att-values-defined-by-appsflyer=valeurs-att-suppl%C3%A9mentaires-d%C3%A9finies-par-appsflyer h_01HGX96RG9NX9QM2WTX8789DDR=valeurs-att-suppl%C3%A9mentaires-d%C3%A9finies-par-appsflyer is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=lat-dans-ios--consid%C3%A9rations-et-comment-lat-se-traduit-en-att-dans-ios-14 h_01HGX9468F0VTYNXBJRSTNBCMB=lat-dans-ios--consid%C3%A9rations-et-comment-lat-se-traduit-en-att-dans-ios-14" />
