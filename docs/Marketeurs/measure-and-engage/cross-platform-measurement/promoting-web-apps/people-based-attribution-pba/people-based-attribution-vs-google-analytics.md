---
title: Attribution basée sur les personnes et Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T13:15:05Z'
  id: 360001305617
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360001305617
---
> **En bref :** les différences entre l'attribution basée sur les personnes (PBA) et Google Analytics

## Les différences entre la PBA et Google Analytics

La PBA et Google Analytics sont des solutions qui permettent l'analyse web et la mesure des conversions. Chacune se concentre sur des aspects de mesure différents. La PBA offre de plus des avantages supplémentaires.

* La PBA est un organe d'attribution indépendant et impartial qui se focalise sur la mesure de l'attribution. La PBA attribue les conversions et les revenus aux sources média ou campagnes qui dirigent les utilisateurs sur votre site.
* Google Analytics se concentre davantage sur l'analyse web. Il rassemble, analyse et agrège les données relatives au comportement des utilisateurs. Avec Google Analytics, vous pouvez par exemple étudier le comportement des utilisateurs, les entonnoirs, les événements web.

### Les avantages de la PBA par rapport à Google Analytics

Les avantages de la PBA par rapport à Google Analytics sont :

* La PBA comprend :
  * La mesure web-to-app. Cette métrique indique le nombre d'utilisateurs qui passent de votre site à votre app. Elle vous dit également quelles sont les sources média et les campagnes qui amènent sur votre site les utilisateurs installeront ensuite votre app.
  * <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports">Les données brutes des conversions et événements</Anchor>, que vous pouvez ensuite importer dans vos propres systèmes de BI. Vous avez ainsi la possibilité d'exécuter votre analyse à votre guise.

### Explication des différences

Pour comparer les données issues de la PBA avec celles de Google Analytics, reportez-vous aux éléments suivants pour connaître les différences en termes de données.

#### Intégration du SDK

La manière dont vous implémentez la PBA et Google Analytics peut affecter la collecte des données.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics affiche plus de sessions et de visiteurs">

#### Cause

Si Google Analytics se charge avant le SDK web, les utilisateurs en mode rebond, ou qui restent très peu de temps sur votre site, ne seront pas comptabilisés dans la PBA. Ce qui provoque des écarts dans les données qui concernent les sessions et les visiteurs.

#### SOLUTION

Nous vous recommandons vivement de positionner le SDK web pour qu'il se charge le plus tôt possible.

Que vous <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#intégration-du-sdk-web-dans-le-site-web">chargiez directement le SDK ou via Google Tag Manager</Anchor>, un chargement tardif du SDK peut entraîner des écarts conséquents.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics affiche plus de données pour les sessions, les campagnes et les conversions">

#### Cause

Le SDK web n'est présent que sur certaines pages. Google Analytics lui est présent sur toutes les pages. De fait, Google Analytics collecte des données sur l'ensemble de votre site tandis que le SDK web ne les récupère que depuis certaines pages. Ce qui provoque des écarts dans les données qui concernent les sessions, les visiteurs, les campagnes et les conversions.

#### SOLUTION

Implémenter le SDK web sur toutes les pages de votre site Web.

</Accordion>

### Paramètres du tableau de bord

Les réglages du tableau de bord de type fuseau horaire ou filtre de données peuvent affecter la manière dont les données vous sont présentées.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Réglages du fuseau horaire : les écarts dans les données">

#### Cause

Si les paramètres de fuseau horaire de votre Google Analytics sont différents de ceux de votre tableau de bord PBA, vous pouvez rencontrer des incohérences.

> 📄 **Exemple**
>
> Votre tableau de bord AppsFlyer est réglè sur UTC et votre tableau de bord GA est configuré sur UTC +13. Votre tableau de bord GA est donc en avance d'une journée par rapport à votre tableau de bord AppsFlyer.
>
> Ainsi, les données affichées dans le tableau de bord AppsFlyer du 2 mars n'apparaitront dans votre tableau de bord GA que si vous choisissez le 3 mars dans le filtre des périodes.

#### SOLUTION

Assurez-vous que les paramètres de fuseau horaire sont identiques dans AppsFlyer et dans Google Analytics.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Filtres de données : divergences dans les données">

#### Problème

Tant AppsFlyer que Google Analytics vous offrent la possibilité de filtrer les données en fonction de la date, des sources média attribuées, campagnes ou événements. Utiliser des filtres différents dans AppsFlyer et dans Google Analytics peut générer un affichage divergent pour les mêmes données.

#### SOLUTION

Lorsque vous comparez les données des deux tableaux de bord, assurez-vous qu'aucun filtre n'est appliqué à l'ensemble des données.

</Accordion>

### Conversions et événements

L'absence de cohérence dans les modèles d'attribution et fenêtres rétrospectives, dans la manière dont vous envoyez les événements et paramétrez les cookies, tout cela peut perturber la collecte et le traitement des données.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Fenêtre rétrospective : incohérences dans la mesure de conversion">

#### Cause

Si vous disposez de fenêtres rétrospectives différentes dans Google Analytics et dans la PBA, des erreurs peuvent se produire dans les données d'attribution.

#### SOLUTION

La fenêtre rétrospective de la PBA est toujours de 30 jours. Assurez-vous de définir une fenêtre rétrospective de 30 jours dans Google Analytics lorsque vous <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">choisissez votre modèle d'attribution</Anchor>.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Fenêtre rétrospective : écarts dans la mesure des conversions">

#### Cause

Des modèles d'attribution différents dans Google Analytics et dans la PBA peuvent produire des incohérences dans les données d'attribution.

#### SOLUTION

Google Analytics propose des <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">modèles d'attribution par défaut</Anchor> parmi lesquels vous pouvez choisir. Cependant, la PBA opère sur un dernier contact non-direct d'une fenêtre rétrospective d'attribution de 30 jours. Assurez-vous de choisir dans Google Analytics un modèle d'attribution de type dernier contact non-direct.

</Accordion>

<div id="sending-events" />

<Accordion title="Envoi d'événements">

#### Problème

Tant le SDK Google Analytics que le SDK web vous permettent d'envoyer des événements. Si vous implémentez une logique d'envoi d'événements à Google Analytics et une autre différente pour la PBA, des écarts peuvent survenir.

#### SOLUTION

Lorsque vous envoyez des événements, vérifiez les points suivants :

* Assurez-vous que le même déclencheur s'applique bien aux deux
* Assurez-vous d'envoyer l'événement à la fois à Google Analytics et à la PBA

Cliquez <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#principes-de-lenregistrement-des-événements">ici</Anchor> pour découvrir comment envoyer des événements à l'aide du SDK web.

</Accordion>

<div id="cookies" />

<Accordion title="Cookies">

La PBA et Google Analytics utilisent tous deux des cookies pour reconnaître les utilisateurs.

#### Réglages des cookies dans Google Analytics

Bien qu'il soit recommandé de laisser le SDK Google Analytics paramétrer automatiquement les cookies, vous pouvez tout de même <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">configurer et modifier les réglages des cookies</Anchor>. Toute modification des paramètres des cookies peut entraîner des inexactitudes.

#### Définir l'expiration des cookies

Google Analytics permet de définir la durée d'expiration des cookies. Si vous paramétrez les cookies de Google Analytics pour qu'ils expirent avant les cookie du SDK web, il y a un risque d'erreur.

> 📄 **Exemple**
>
> Mark visite régulièrement votre site depuis plus d'un an et il envisage de s'abonner à votre contenu premium.
>
> Votre développeur configure le cookie de Google Analytics pour qu'il expire au bout d'un an. Mais le SDK web lui définit le cookie pour qu'il se termine au bout de deux ans.
>
> Lorsque Mark prend finalement son abonnement et que la conversion est enregistrée, le cookie de Google Analytics n'est plus valide ce qui fait qu'un autre est défini à sa place.
>
> Il en résulte que Google Analytics affiche deux utilisateurs, qui sont en fait tous les deux Mark, avec un seul d'entre eux qui a une conversion associée. La PBA par contre voit Mark comme un seul utilisateur, qui est celui qui a une conversion qui lui est associée.
>
> Cela signifie que votre taux de conversion dans Google Analytics sera inférieur à celui de la PBA.

#### Définir un cookie à un sous-domaine

Google Analytics vous permet de définir des cookies aux sous-domaines tandis que la PBA ne peut les définir qu'aux domaines principaux.

> 📄 **Exemple**
>
> Vous définissez un cookie au sous-domaine **boutique.monsite.com**. Sharon visite votre site puis se rend dans votre boutique en ligne sur **boutique.monsite.com**. Google Analytics la considèrera **comme deux utilisateurs différents**.
>
> Étant donné que la PBA ne définit les cookies que sur le domaine principal **monsite.com**, il voit Sharon sur **monsite.com** et sur **boutique.monsite.com** comme un seul et même utilisateur.
>
> Résultat : il apparait deux utilisateurs dans Google Analytics et un seul dans la PBA.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=les-diff%C3%A9rences-entre-la-pba-et-google-analytics benefits-of-pba-over-google-analytics=les-avantages-de-la-pba-par-rapport-%C3%A0-google-analytics reasons-for-differences=explication-des-diff%C3%A9rences sdk-implementation=int%C3%A9gration-du-sdk cause::49d3e519=cause-1 solution::447e7ac9=solution-1 dashboard-settings=param%C3%A8tres-du-tableau-de-bord cause::30244d2c=cause-2 solution::f1a0e066=solution-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=probl%C3%A8me solution::df8f3921=solution-3 conversions-and-events=conversions-et-%C3%A9v%C3%A9nements cause::b346571c=cause-3 solution::4bb14ac9=solution-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=cause-4 solution::b2be4a33=solution-5 issue::b412f5ba=probl%C3%A8me-1 solution::39b4d7d6=solution-6 cookie-settings-in-google-analytics=r%C3%A9glages-des-cookies-dans-google-analytics setting-cookie-expiration=d%C3%A9finir-lexpiration-des-cookies setting-cookie-subdomain=d%C3%A9finir-un-cookie-%C3%A0-un-sous-domaine" />
