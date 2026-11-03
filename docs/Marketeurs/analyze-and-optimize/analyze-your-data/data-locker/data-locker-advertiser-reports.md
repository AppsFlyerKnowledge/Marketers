---
title: Rapports des annonceurs de Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2023-11-12T12:51:32Z'
  id: 4410643856657
  locale: fr
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/fr/articles/4410643856657
---
> **En bref :** les rapports de données brutes et rapports agrégées disponibles via Data Locker

## Rapports disponibles via Data Locker pour les annonceurs

<table><thead><tr><th>Type de données</th><th>Groupe de rapport</th><th>Abonnement à Data Locker requis</th></tr></thead><tbody><tr><td>Brut</td><td>Parcours de l'utilisateur - données brutes</td><td>Oui (2)</td></tr><tr><td>Brut</td><td>Protect360</td><td>Oui</td></tr><tr><td>Brut</td><td>Attribution basée sur les personnes (PBA)</td><td>Non (1)</td></tr><tr><td>Brut</td><td>Incrementality</td><td>Non (1)</td></tr><tr><td>Brut</td><td>SKAN</td><td>Non (1)</td></tr><tr><td>Brut</td><td>Revenus publicitaires</td><td>Oui</td></tr><tr><td>Brut</td><td>CTV</td><td>Oui</td></tr><tr><td>Agrégées</td><td>Analyse de cohorte</td><td>Non (1)</td></tr><tr><td colspan="3"><p>(1) Si vous n'avez pas l'abonnement Data Locker, vous devez fournir un stockage <a href="./data-locker-for-marketers#storage-options" target="_blank">dont vous êtes propriétaire</a>.</p><p>(2) À l'exception des engagements multiplateformes</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Explications sur l'actualisation des données">

Ce qui suit détaille les termes relatifs à l'actualisation des données utilisés dans l'article. 

| Termes | Détails |
| --- | --- |
| 1-3 heures | <ul><li>Temps de préparation des rapports :<ul><li>95 % des rapports sont réalisés et disponibles dans le compartiment dans l'heure qui suit l'événement.</li><li>99% des rapports sont prêts et accessibles dans le compartiment dans les 3 heures qui suivent l'événement.</li></ul></li></ul> |
| Désinstallation quotidienne | <ul><li>Les données de désinstallation sont préparées chaque jour.</li><li>Généralement disponible entre 10:00 et 12:00 UTC.</li><li>Généralement inscrit dans le dossier h=2. En d'autres termes, le dossier h=2 contient les désinstallations signalées le jour précédent. Les données peuvent cependant être inscrites dans un dossier créé ensuite, votre processus d'importation doit donc lire les données contenues dans chaque dossier du dossier des désinstallations. C'est-à-dire h=1-24 et h=late Par exemple, le rapport concernant les données générées le lundi se trouve dans le dossier « Mardi h=2 ». Les données sont disponibles le mardi après 10:00 UTC.</li></ul> |
| Quotidien+1 | Les données de revenus publicitaires sont disponibles après 1 journée. Les données générées le lundi seront donc disponibles dans le dossier h=23 du lundi à partir de 20:00 UTC le mardi. Cf <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">Actualisation des données des revenus publicitaires</Anchor> |

</Accordion>

## Rapports de données brutes

<div id="user-journey" />

<Accordion title="Parcours utilisateur">

Pour obtenir une description des types de rapports, cf <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Rapports du parcours utilisateur</Anchor>.

| Catégorie | Type de rapport (sujet) | Actualisation des données | Organique / Non-Organique | Propre à Data Locker |
| --- | --- | --- | --- | --- |
| Acquisition des utilisateurs | Clics | 1-3 heures | S/O | ✓ |
| Retargeting | Clics | 1-3 heures | S/O | ✓ |
| Acquisition des utilisateurs | Impressions | 1-3 heures | S/O | ✓ |
| Retargeting | Impressions | 1-3 heures | S/O | ✓ |
| Acquisition des utilisateurs | d'installations | 1-3 heures | Les deux |  |
| Acquisition des utilisateurs | Évènements in-app | 1-3 heures | Les deux |  |
| Acquisition des utilisateurs | Revenus publicitaires attribués | Quotidien+1 | Non organique |  |
| Acquisition des utilisateurs | Revenus publicitaires organiques | Quotidien+1 | Trafic |  |
| Retargeting | Revenus publicitaires de retargeting | Quotidien+1 | Non organique |  |
| Retargeting | Conversions | 1-3 heures | Non organique |  |
| Retargeting | Évènement in-app | 1-3 heures | Non organique |  |
| Retargeting | Sessions | 1-3 heures | Les deux | ✓ |
| Acquisition des utilisateurs | Sessions | 1-3 heures | Les deux | ✓ |
| Acquisition des utilisateurs | Désinstallations | Désinstallation quotidienne | Non organique |  |
| Acquisition des utilisateurs | Désinstallations organiques | Désinstallation quotidienne | Trafic |  |
| Réinstallations | Réinstallations | 1-3 heures | Non organique |  |
| Réinstallations | Réinstallations organiques | 1-3 heures | Trafic |  |
| Acquisition des utilisateurs | Engagements multiplateformes | Par heure | Les deux | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

Cf <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">À propos des rapports Protect360</Anchor>

| Type de rapport (sujet) | Actualisation des données |
| --- | --- |
| Installations bloquées | 1-3 heures |
| Événements in-app bloqués | 1-3 heures |
| Clics bloqués | 1-3 heures |
| Installations post-attribution | Quotidien<br /><br />Chaque jour, le rapport contient les installations post-attribution enregistrées le jour précédent. Par exemple, le rapport qui concerne les données générées le lundi se trouve dans le rapport du mardi. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="People-Based Attribution">

**Actualisation des données**

Quotidiennement disponible entre 10 et 12 heures après le jour précédent (00:00 UTC). Par exemple, les données reçues un lundi sont traitées après la fin de la journée, et sont enregistrées dans le dossier du lundi h=23. Les données seront disponibles après 12:00 UTC le mardi.

**Attention**

* Les données de tous les bundles de marques PBA du compte sont toujours fournies sans tenir compte du filtre de l'application.
* Le regroupement des données par application n'est pas disponible.

| Type de rapport (sujet) |
| --- |
| <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports#website-visits-and-website-events">Visites du site web</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports#website-visits-and-website-events">Événements sur le site web</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Installations assistées par site web</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports#conversion-paths">Chemins de conversion</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Incrementality">

Cf <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#available-reports">Rapports d'incrémentalité</Anchor>

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

À propos des <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">Rapports de données brutes SKAN</Anchor>

**Actualisation des données**

* Les données sont disponibles soit le lendemain du jour où le postback est reçu par AppsFlyer, soit le lendemain du jour où les données sont transmises à AppsFlyer par l'API.
* Les données sont contenues dans le dossier h=23 du jour où les données sont reçues par AppsFlyer. Exemple : un postback reçu le lundi est traité après la fin de la journée. Le traitement se termine le mardi à 12:00 UTC et les données sont mises à disposition dans le dossier du lundi h=23.

| Type de rapport (sujet) |
| --- |
| Les postbacks |
| Copie des postbacks (envoyés directement par iOS à AppsFlyer) |
| d'installations |
| [PLEASE TRANSLATE] |
| Évènements in-app |
| Dimensions publicitaires SRN |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Revenus publicitaires">

Cf <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Données brutes des revenus publicitaires</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="Plateformes CTV, PC et console (3)">

Cf <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-data-via-data-locker">Les données des plateformes CTV, PC et console via Data Locker</Anchor>

</Accordion>

## Rapports agrégés

<div id="cohort-analytics" />

<Accordion title="Analyse de cohorte">

**Actualisation des données**

* Les rapports sont inscrits dans le dossier h=23.
* Les rapports sont généralement disponibles entre 10:00 et 12:00 UTC dans le dossier h=23 du jour qui précède.
* Le traitement se termine le mardi à 12:00 UTC, les données sont mises à disposition dans le dossier du lundi mais ne sont pas placées dans un dossier «h».

| Type de rapport (sujet) |
| --- |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Cohorte unifiée</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Cohortes d'acquisition d'utilisateurs</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Retargeting des cohortes</Anchor> |

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=rapports-disponibles-via-data-locker-pour-les-annonceurs 01H7WFZN6P1S49NYX8Q0W55P0B=rapports-disponibles-via-data-locker-pour-les-annonceurs 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=rapports-de-donn%C3%A9es-brutes 01H7WFZN6P94YW1V79NT3HV5G4=rapports-de-donn%C3%A9es-brutes 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv aggregated-reports=rapports-agr%C3%A9g%C3%A9s 01H7WFZN6Q90AT8N0VY5PKQ407=rapports-agr%C3%A9g%C3%A9s 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics" />
