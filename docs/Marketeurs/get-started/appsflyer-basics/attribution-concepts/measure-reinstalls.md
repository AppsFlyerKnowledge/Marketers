---
title: Réinstallations
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
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2023-08-21T08:06:46Z'
  id: 10164066030737
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/10164066030737
---
> **En bref**: une réinstallation se produit lorsqu'un utilisateur installe une appli, la désinstalle, puis la réinstalle à nouveau. Les réinstallations donnent lieu à l'un des types d'attribution suivants : réinstallation non organique, réinstallation organique ou réattribution (retargeting). Les réinstallations permettent de ne pas avoir à payer deux fois pour les utilisateurs qui désinstallent et installent à nouveau.

<div id="what-is-a-reinstall" />

## Qu'est-ce qu'une réinstallation ?

Une réinstallation se produit lorsqu'un utilisateur supprime une application puis la réinstalle au cours de la fenêtre de réattribution <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#re-attribution-window">.</Anchor>

La réinstallation peut provenir d'une campagne de retargeting (réattribution), d'une source organique ou d'une source non organique.

Les réinstallations qui proviennent d'une source organique ou d'une source non organique et qui ont lieu dans la fenêtre de réattribution sont appelées «réinstallations».

Les réinstallations qui proviennent des campagnes de retargeting sont appelées «réattributions».

La différence est donc la manière dont les événements de réinstallation et in-app sont attribués.

Si une installation a lieu en dehors de la fenêtre de réattribution , la réinstallation est appelée <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#new-install">«nouvelle installation»</Anchor>. Une nouvelle installation est attribuée à la source média (ou organique si aucun engagement n'a été enregistré) et une nouvelle fenêtre de réattribution s'ouvre.

Le tableau ci-dessous indique comment AppsFlyer catégorise les différentes réinstallations

| Source de la réinstallation | La fenêtre de réattribution est-elle appliquée ? | L'utilisateur a-t-il interagi avec une campagne de retargeting avant de réinstaller ? | L'utilisateur a-t-il interagi avec une campagne UA avant de réinstaller ? | Appellation |
| --- | --- | --- | --- | --- |
| Depuis une campagne de retargeting | Oui | Oui | Non | Réattribution |
| Depuis une source organique ou non organique | Oui | Non | Oui et non | Réinstallation |
| Depuis une source organique ou non organique | Non | Non | Oui et non | Nouvelle installation |

<div id="why-are-reinstalls-important" />

## Pourquoi les réinstallations sont-elles importantes ?

En plus de démontrer que les utilisateurs reviennent sur votre application et que vos campagnes sont efficaces, l'attribution correcte d'une réinstallation est importante pour éviter aux utilisateurs qui désinstallent et réinstallent dans la fenêtre de réattribution de payer deux fois.<Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#re-attribution-window">.</Anchor>

De même, l'attribution des événements in-app issus de réinstallation à la source média originale (première installation) permet aux annonceurs d'avoir une meilleure compréhension de l'engagement des utilisateurs. c'est aussi un bon indicateur de l'efficacité des campagnes UA et des publicités de retargeting. Pour plus d'informations, consultez la section [événements in-app](/docs/measure-reinstalls#évènement-in-app) ci-dessous.

<div id="reinstall-flow-and-outcome" />

## Processus de réinstallation et résultats

<div id="reinstall" />

<Accordion title="Réinstallation">

Après la première installation de l'app, l'utilisateur la désinstalle, puis la réinstalle au cours de la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#re-attribution-window">fenêtre de réattribution.</Anchor> Une réinstallation peut provenir d'une campagne organique ou d'une campagne UA (cf nos exemples ).

Voici ce qu'il en résulte :

* L'installation n'est PAS attribuée : elle n'apparaît ni sur le tableau de bord, ni dans les données.
* AUCUN postback d'installation n'est envoyé aux sources média.
* Consulter la section [événements in-app](/docs/measure-reinstalls#évènement-in-app) pour savoir comment les événements in-app sont attribués.

</Accordion>

<div id="reattribution" />

<Accordion title="Réattribution">

Après la première installation de l'app, l'utilisateur la désinstalle, puis s'engage dans une campagne de retargeting et la réinstalle à nouveau pendant la fenêtre de réattribution.  

Voici ce qu'il en résulte :

* L'installation est attribuée à la source média de retargeting et s'affiche dans les vues retargeting et Unifiée du tableau de bord général.
  * La vue Acquisition d'utilisateurs n'inclut pas les réattributions
* Tous les événements in-app qui suivent sont attribués à la source média de retargeting (cf chapitre [événements in-app](/docs/measure-reinstalls#évènement-in-app) pour plus d'informations)
* Un postback d'installation est envoyé à la source média de retargeting.

Pour plus d'informations sur l'attribution de retargeting, cliquez <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">ici</Anchor>.

</Accordion>

<div id="postreinstall-events-attribution-state" />

<div id="note" />

<div id="post-reinstall-in-app-events" />

## Évènement in-app

### Présentation

<Image align="center" alt="" src="https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg" />

Les événements in-app produits par un utilisateur suite à une réinstallation sont soit attribués à des événements organiques ou non organiques, soit non attribués à des événements organiques en fonction du statut d'attribution des événements post réinstallation (cf détails ci-dessous).

Exemple d'événement in-app : un utilisateur qui réinstalle une app puis effectue un achat in-app.

#### Les événements in-app et leur système d'attribution

<table><tbody><tr><th>Statut d'attribution des événements post réinstallation</th><th>Après une réinstallation</th><th>Après une réattribution</th></tr><tr><td><strong>Attribué comme in-app organique</strong></td><td>Organique non attribué</td><td>Retargeting</td></tr><tr><td> <strong>Attribué à la première installation</strong><span> (1)</span> </td><td>Source média de la première installation</td><td>Retargeting <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) Voir les restrictions ci-dessous</span></p><p><span>(2) Dans le champ de la source primaire. La source média de la première installation sera affichée dans le champ de la source secondaire (<span>uniquement dans les données brutes).</span></span></p></td></tr></tbody></table>

<div id="unattributed-organic-inapps" />

<Accordion title="In-app organiques non attribués">

Réinstallation

* Tous les événements in-app sont comptés comme organiques, ou complètement ignorés en fonction du tableau de bord.
* Les événements in-app seront transmis avec le type de conversion et le type de campagne marqués comme "*inconnu*."
* La date à laquelle les données sont agrégées dépend de l'événement :
  * Pour la majorité des événements in-app issus d'un SDK c'est la date qui correspond au téléchargement de l'app qui est utilisée pour agréger les données, et non la date de réinstallation.
  * Pour les événements de revenus publicitaires (af\_ad\_revenue) transmis par le connecteur SDK, c'est la date de réinstallation qui est utilisée pour agréger les données.

Réattribution

* Tous les événements in-app sont attribués à la source média de retargeting.

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Attribué à la première installation">

> 🚧 **Conditions préalables**
>
> Nécessite une activation. Contactez votre CSM pour en discuter.

#### Objectif

Fournit aux annonceurs une meilleure vision de l'engagement des utilisateurs. Montre l'efficacité des campagnes UA et des publicités de retargeting lorsque les événements in-app sont attribués à la source d'origine plutôt qu'à l'organique.

#### Réinstallation

* Tous les événements in-app générés par les réinstallations sont attribués à l'installation d'origine (1)

#### Réattribution

* Tous les événements in-app sont attribués à la publicité de retargeting dans la source primaire et à l'installation d'origine dans la source secondaire. (2)

(1) Voir les restrictions [ci-dessous.](/docs/measure-reinstalls#limitations)

(2) Ne s'affiche que dans les données brutes.

<div id="note-1" />

#### Remarque

Les données des KPI organiques affichées dans le tableau de bord peuvent avoir une valeur inférieure quand l'**attribution des événements post réinstallation** est réglée sur **Attribué à la première installation** puisque certains des résultats peuvent être attribués à une source média non organique.

</Accordion>

<div id="examples" />

<Accordion title="Exemples">

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<div id="examples-for-first-install-mode-attribution" />

#### Avec **«Attribué à la première installation»** activé.

**Exemple 1**

Un utilisateur installe l'app (jour 0), effectue un achat de 10 dollars, puis désinstalle l'app.

Le jour suivant (jour 1), l'utilisateur réinstalle l'app et effectue un achat de 5 dollars.

<Image align="center" alt="Reinstall_1.jpg" src="https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg" />

Puisque l'utilisateur a déjà effectué un achat avant la réinstallation, on ne comptera pas d'utilisateur unique en plus.

| Source média | utilisateurs | Af\_purchase :<br /><br />Utilisateurs uniques<br /><br />Jour 0 | Af\_purchase :<br /><br />Utilisateurs uniques<br /><br />Jour 1 (cumulé) | Revenu<br /><br />Jour 0 | Revenu<br /><br />Jour 1 (cumulé) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | 10 $ | 15 $ |

Nous verrons une augmentation du revenu pour le même `device_identifier`.

| Appsflyer\_id | ID d'appareil | Source média | Nom de l'événement | Date de l’événement |
| --- | --- | --- | --- | --- |
| TEST TRADUCTION | XXX | media\_source\_A | install | jour 0 |
| TEST TRADUCTION | XXX | media\_source\_A | af\_purchase | jour 0 |
| 222 | XXX | organique | reinstall | jour 1 |
| 222 | XXX | media\_source\_A | af\_purchase | jour 1 |

**Exemple 2**

Un utilisateur installe l'app (jour 0), effectue un achat puis désinstalle l'app.

Le jour suivant (jour 1), l'utilisateur réinstalle l'application depuis une campagne UA et effectue un achat.

| Source média | Nom de l'événement | Date de l’événement | Attribution de réinstallation | Attribution d'événements in-app |
| --- | --- | --- | --- | --- |
| media\_source\_A | install | jour 0 | media\_source\_A |  |
| media\_source\_A | af\_purchase | jour 0 |  | media\_source\_A |
| media\_source\_B | reinstall | jour 1 | media\_source\_B |  |
| media\_source\_B | af\_purchase | jour 1 |  | media\_source\_A |

</Accordion>

<div id="limitations" />

<Accordion title="Restrictions">

* Seuls les utilisateurs qui ont accepté de partager leur ID d'appareil avec l'app (ex. IDFA ou GAID) pour l'installation et la réinstallation verront leurs événements in-app attribués à l'installation d'origine.
  * Les ID d'appareils de la première installation et de la réinstallation doivent correspondre.
* La réinstallation doit avoir lieu dans la <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#reengagement-rules-and-windows">fenêtre de réattribution</Anchor> de la dernière installation qui a été enregistrée.
* Les événements de revenus publicitaires sont attribués comme étant organiques
* Chaque installation et réinstallation aura toujours son propre `appsflyer_id.`
* Les tableaux de bord ne font pas de différence entre un événement in-app post installation et une réinstallation.
  * Pour avoir le détail il faut consulter les données brutes

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## Comment les données apparaissent-elles dans les tableaux de bord AppsFlyer ?

<table><tbody><tr><th colspan="2"> </th><th>Réinstallation non organique</th><th>Réinstallation organique</th><th>Réattribution</th></tr><tr><td colspan="2">La réinstallation elle-même</td><td>Non visible</td><td>Non visible</td><td><span>Source média de retargeting</span></td></tr><tr><td rowspan="2">Les attributions d'événements in-app à venir</td><td>Événements post réinstallation définis sur <strong>Attribués comme in-apps organiques</strong> </td><td>Organique non attribué</td><td>Organique non attribué</td><td><span>Source média de retargeting</span></td></tr><tr><td>Événements post réinstallation définis sur <strong>Attribués à la première installation</strong> </td><td>Première source média</td><td>Première source média</td><td>Campagne de retargeting</td></tr><tr><td colspan="5">\*Uniquement dans le tableau de bord général.</td></tr></tbody></table>

<div id="reinstalls-raw-data-reports" />

## Rapports de données brutes des réinstallations

<div id="prerequisites" />

> 🚧 **Conditions préalables**
>
> Nécessite une activation. Contactez votre CSM pour en discuter.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">Exemple de rapport des réinstallations au format CSV</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### Comment l'installation et les événements in-app sont attribués

<table><tbody><tr><th colspan="2"> </th><th>Réinstallation non organique</th><th>Réinstallation organique</th><th>Réattribution</th><th>Installations non organiques</th><th>Installations organiques</th></tr><tr><td colspan="2">Attribué à </td><td>Campagne UA</td><td>Trafic</td><td>Campagne de retargeting</td><td>Campagne UA</td><td>Trafic</td></tr><tr><td rowspan="2">L'attribution des événements à venir</td><td>Événements post réinstallation définis sur <strong>Attribués comme in-apps organiques</strong> </td><td>Trafic</td><td>Trafic</td><td>Campagne de retargeting</td><td>Campagne UA</td><td>Trafic</td></tr><tr><td>Événements post réinstallation définis sur <strong>Attribués à la première installation</strong> </td><td>Première installation</td><td>Première installation</td><td>Campagne de retargeting</td><td>Campagne UA</td><td>Trafic</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### Disponibilité des rapports de réinstallation

* Les rapports de données brutes des réinstallations sont fournis par les outils décrits dans le tableau suivant.
* Les rapports ont la même structure que les rapports d'installation et sont remplis de la même manière :
  * Les champs de la **source média** sont renseignés d'après la source média à l'origine de la réinstallation ou de l'organique.
  * **Heure de l'installation**: identique à l'heure de réinstallation, c'est-à-dire l'heure où l'app a été ouverte la première fois après la réinstallation.
  * **Nom de l'événement :** *reinstall*

| Méthode d'édition du rapport | Réinstallations non organiques | Réinstallations organiques |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Données d'exportation</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">API Pull</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor> | ✓ | ✓ |
| API Push | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=quest-ce-quune-r%C3%A9installation 01H7SZVZPGHBQ7VM8TMWRD3CE4=quest-ce-quune-r%C3%A9installation why-are-reinstalls-important=pourquoi-les-r%C3%A9installations-sont-elles-importantes 01H7SZVZPG6T2AW9B3EMT29AQQ=pourquoi-les-r%C3%A9installations-sont-elles-importantes reinstall-flow-and-outcome=processus-de-r%C3%A9installation-et-r%C3%A9sultats 01H7SZVZPGVQCNCQ7TCZMYM33T=processus-de-r%C3%A9installation-et-r%C3%A9sultats 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=%C3%A9v%C3%A8nement-in-app 01H7SZVZPGBYRWZGAZRT36EFGH=%C3%A9v%C3%A8nement-in-app overview=pr%C3%A9sentation 01H7SZVZPGK7X1NXW467CZP1KJ=pr%C3%A9sentation inapp-events-and-how-they-are-attributed=les-%C3%A9v%C3%A9nements-in-app-et-leur-syst%C3%A8me-dattribution 01H7SZVZPHW7E5WV9C643BG6YB=les-%C3%A9v%C3%A9nements-in-app-et-leur-syst%C3%A8me-dattribution 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install 01H7SZVZPHBQ7E3R107EB2KXES=conditions-pr%C3%A9alables purpose=objectif 01H7SZVZPHXBX6J2APBXS30CPX=objectif reinstall::7f2d499b=r%C3%A9installation 01H7SZVZPHRJ9WPW3TCYECK50W=r%C3%A9installation reattribution::bbb1aabb=r%C3%A9attribution 01H7SZVZPHZFY9ZDEQYP967C2D=r%C3%A9attribution 01H7SZVZPH5YGSMPGW7NPKXJAF=remarque 01H7SZVZPHF3R44DTHCD9QHPR8=examples with-attributed-to-the-first-install-enabled=avec-attribu%C3%A9-%C3%A0-la-premi%C3%A8re-installation-activ%C3%A9 01H7SZVZPHH3DS9J4VRD70VTX6=avec-attribu%C3%A9-%C3%A0-la-premi%C3%A8re-installation-activ%C3%A9 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=comment-les-donn%C3%A9es-apparaissent-elles-dans-les-tableaux-de-bord-appsflyer 01H7SZVZPHHQS4NHEDATD7ZP9V=comment-les-donn%C3%A9es-apparaissent-elles-dans-les-tableaux-de-bord-appsflyer reinstalls-raw-data-reports=rapports-de-donn%C3%A9es-brutes-des-r%C3%A9installations 01H7SZVZPHPWN8REBQ5CWVFNJT=rapports-de-donn%C3%A9es-brutes-des-r%C3%A9installations 01H7SZVZPHCVDPDDYD6HHNFMMK=conditions-pr%C3%A9alables-1 how-the-install-and-inapp-events-are-attributed=comment-linstallation-et-les-%C3%A9v%C3%A9nements-in-app-sont-attribu%C3%A9s 01H7SZVZPHQT8XS3ZBA4W682GB=comment-linstallation-et-les-%C3%A9v%C3%A9nements-in-app-sont-attribu%C3%A9s availability-of-reinstall-reports=disponibilit%C3%A9-des-rapports-de-r%C3%A9installation 01H7SZVZPH6NY7FMG9YHDBB95R=disponibilit%C3%A9-des-rapports-de-r%C3%A9installation" />
