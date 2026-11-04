---
title: Le comptage des sessions
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2024-07-02T11:10:06Z'
  id: 360000520785
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/360000520785
---
> **En bref :** La mesure des sessions est utilisée par les annonceurs pour mesurer l'engagement des utilisateurs d'applications au cours d'une période donnée.

<Image alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

<div id="sessions-counting-principles" />

## Principes de comptage des sessions

Le nombre de sessions, ou lancements, effectuées par les utilisateurs est un indicateur important qui sert à mesurer l'engagement des utilisateurs envers l'application. Elle est disponible via plusieurs rapports et tableaux de bord. Les sessions sont utilisées pour calculer les paramètres suivants :

* Utilisateurs actifs quotidiens (DAU)
* Utilisateurs actifs mensuels (MAU)
* Rétention
* Utilisateurs loyaux utilisant le réglage par défaut de l'ouverture de 3 applications

**Attention !** Dans le cas des sessions organiques, l'indicateur est disponible dans les tableaux de bord Activité et Cohorte, mais pas dans le tableau de bord Vue d'ensemble.

<div id="sessions-calculation" />

### Calcul des sessions

La mesure des sessions est calculée à l'aide de l'événement *af\_app\_opened* reporté par le SDK. Un intervalle minimal entre les sessions contrôle les sessions enregistrées côté serveur.

L'*événement af\_app\_opened* s'affiche comme un *lancement* dans les données brutes des sessions disponibles via Data Locker. Les sessions ne sont pas disponibles via d'autres outils de reporting. Pour faciliter la compréhension, nous utiliserons dans cet article le terme *af\_app\_opened*.

**Rapport sur les sessions**

Une session est signalée par le SDK lorsque l'une des situations suivantes se produit :

* L'utilisateur lance l'app.
* Lorsque l'app passe de l'arrière-plan au premier plan. Le développeur peut modifier le comportement des rapports en appelant [setMinTimeBetweenSessions](/docs/measure-sessions#session-reporting-by-the-app-sdk) .
* Un rapport de session explicite par le développeur dans les applications Android. C'est le cas, par exemple, des applications utilitaires qui sont toujours en arrière-plan.

**Mesure des sessions**

La métrique des sessions est comptabilisée en tenant compte d'un mécanisme de temps minimum entre les sessions avec une durée par défaut de 10 minutes comme décrit dans l'exemple qui suit.

<div id="minimum-time-between-sessions-mechanism" />

## Mécanisme de délai minimum entre les sessions

Le mécanisme a une incidence sur le nombre de sessions. **Attention !** Si le temps minimum entre deux sessions est long (plus d'une heure) et que les utilisateurs n'ouvrent pas l'application plusieurs fois par jour, certains indicateurs liés aux sessions, tels que le DAU et la fidélisation, peuvent être affectés. Cela est particulièrement vrai dans le cas des applications que les utilisateurs ouvrent généralement une fois par jour.

<div id="description-and-example" />

<Accordion title="Description et exemple">

Le mécanisme régit les sessions qui sont comptabilisées. Une session est comptabilisée si le temps minimum autorisé entre les sessions s'est écoulé.

Le flux est le suivant : Une session est comptée → Un compte à rebours démarre → Les sessions signalées pendant le compte à rebours ne sont pas prises en compte.

**Exemple**

Supposition: Le délai minimum autorisé entre les réglages des sessions est de 10 minutes.

| Exemple de cas | Heures d’enregistrement de la session (nombre de minutes depuis 00:00) | Nombre de sessions comptabilisées | Les sessions ne sont pas prises en compte |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | Aucun |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="Réglage de la minuterie">

* Valeur par défaut : 10 minutes
* Les valeurs possibles sont les suivantes :

  * &lt;1-60 Minutes
  * 1-24 heures

**Pour définir le temps minimum autorisé entre les sessions :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > **Paramètres de l'application**.
2. Définir le **délai minimum entre les sessions**.
3. Cliquez sur **Enregistrer les paramètres**.   
   Le changement prend effet dans l'heure.

</Accordion>

<div id="sessions-related-topics" />

## Thèmes liés aux sessions

<div id="retargeting-sessions" />

<Accordion title="Sessions de retargeting">

* Les sessions de retargeting sont disponibles à partir du 12 juillet 2020.
* Sessions de retargeting disponibles
  * Retargeting et type de vue unifiée dans le tableau de bord.
  * Les vues de la cohorte concernée, c'est-à-dire retargeting et unifié. 
    * Dans le cas d'un affichage unifié, si les sessions ont été attribuées à un UA et à une source média de retargeting, la source média de retargeting prévaut et l'UA ne s'affiche pas.
    * Fraîcheur des données* Tous les jours à 13:00 UTC.
  * Data Locker : Les rapports sur les sessions de retargeting peuvent être activés ; ils comprennent les sessions de réengagement et de réattribution.
    * Fraîcheur des données* Décalage de 6 heures.
* Pendant les fenêtres de réengagement, les sessions sont attribuées à la fois à l'UA et à la source média de retargeting. De même, d'autres événements de réengagement in-app sont <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">doublement attribués</Anchor>.
* Dans le cas de Google Ads et X Ads, pour éviter les postbacks dupliqués, l'événement *af\_app\_opened* n'est envoyé qu'une seule fois.

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="Sessions postbacks de sessions vers les partenaires">

Vous pouvez envoyer des postbacks de sessions partenaires de manière à ce qu'un <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">postback</Anchor> soit envoyé pour chaque session comptabilisée.

* Pour envoyer le postback : associer explicitement *af\_app\_opened* à un événement partenaire. Attention ! Dans le rapport de données brutes d'AppsFlyer disponible via Data Locker, cet événement est considéré comme un *lancement*.
* Il faut tenir compte du fait qu'il s'agit d'un événement à fort volume et que de nombreux partenaires ne souhaitent pas le recevoir.

<div id="note" />

> 📘 **Remarque**
>
> Le mappage de `af_app_opened` n'est pris en charge que par les partenaires dont les **sessions d'envoi** sont activées.

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="Rapport de session par l'application (SDK)">

**Côté application :** Le SDK envoie *af\_app\_opened* chaque fois que l'application est ouverte ou mise au premier plan après avoir pris en compte le paramètre *setMinTimeBetweenSessions du* SDK.

**Côté serveur :** Les sessions rapportées par l'application sont comptées et enregistrées après avoir pris en compte le mécanisme de temps minimum entre les sessions. Les sessions comptabilisées sont attribuées selon les mêmes <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">règles d'attribution</Anchor> que les autres événements in-app.

<div id="explicit-sessions-reporting-by-the-developer-android-apps-only" />

#### **Signalement explicite des sessions par le développeur (applications Android uniquement)**

Utilisez <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession">logSession</Anchor> dans Android pour signaler explicitement une session. Un appel équivalent n'est pas disponible sous iOS.

* Les applications qui fonctionnent en permanence en arrière-plan peuvent nécessiter une certaine logique mise en œuvre par le développeur pour signaler les sessions. Par exemple, les applications utilitaires telles que les économiseurs de batterie, les lanceurs, les verrouillages d'écran et les applications antivirus. Pour ces types d'applications, envisagez de déclarer une session tous les jours à minuit ou à un autre intervalle approprié à l'application.
* Dans d'autres cas, vous pouvez vouloir compter les sessions lorsque les utilisateurs effectuent une action dans l'application, par exemple en appuyant sur le bouton d'*effacement de la mémoire*, etc.

<div id="setting-minimum-time-between-app-launches" />

#### **Fixer un délai minimum entre les lancements d'applications**

Dans le SDK, définissez le temps minimum qui peut s'écouler entre deux sessions pour qu'elles soient signalées séparément.

Utiliser ***setMinTimeBetweenSessions,*** c'est-à-dire l'événement af\_app\_opened, pour contrôler le temps minimum qui doit s'écouler entre les sessions afin que chacune d'entre elles soit signalée.

* [Par défaut] cinq secondes. Cela signifie qu'au moins 5 secondes doivent s'écouler avant qu'une autre session ne soit signalée.
* L'API permet de définir le temps minimum requis entre les sessions.

**Le `setMinTimeBetweenSessions` référence SDK :**

<Tabs>
<Tab title="Android">

Voir[`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions) dans la référence du SDK Android

</Tab>

<Tab title="iOS">

Voir [`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions) dans la référence du SDK iOS

</Tab>

<Tab title="Unity">

Voir [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions) référence du SDK Unity pour

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=principes-de-comptage-des-sessions h_01HB8NDPNKERK1RR1Y09V2R2CC=principes-de-comptage-des-sessions sessions-calculation=calcul-des-sessions h_01HB8NDPNKFW6S28A3TC7W5J3C=calcul-des-sessions minimum-time-between-sessions-mechanism=m%C3%A9canisme-de-d%C3%A9lai-minimum-entre-les-sessions h_01HB8NDPNKF32E34M3CBJ6GMP8=m%C3%A9canisme-de-d%C3%A9lai-minimum-entre-les-sessions h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=th%C3%A8mes-li%C3%A9s-aux-sessions h_01HB8NDPNKPTJX56Q2SVAB6V6T=th%C3%A8mes-li%C3%A9s-aux-sessions h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=remarque h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=signalement-explicite-des-sessions-par-le-d%C3%A9veloppeur-applications-android-uniquement h_01HB8NTFMR3Y9GHFP3EWMAATHY=signalement-explicite-des-sessions-par-le-d%C3%A9veloppeur-applications-android-uniquement setting-minimum-time-between-app-launches=fixer-un-d%C3%A9lai-minimum-entre-les-lancements-dapplications h_01HB8NTMC1JYPDWYG9YC8RNSEQ=fixer-un-d%C3%A9lai-minimum-entre-les-lancements-dapplications" />
