---
title: Attribution des invitations utilisateur
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2023-10-04T13:29:17Z'
  id: 115004480866
  locale: fr
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/fr/articles/115004480866
---
> **En bref :** attribuez et enregistrez les nouvelles installations provenant d'invitations d'utilisateurs existants à utiliser vos apps.

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

<div id="about-user-invite-attribution" />

## À propos de l'attribution des invitations d'utilisateurs

Les invitations d'utilisateurs ont lieu lorsque les utilisateurs existants de votre app partagent des liens qui redirigent les personnes (comme leurs amis) vers le téléchargement/l'ouverture de votre application.

L'attribution d'invitations d'utilisateurs se fait lorsque vous attribuez une nouvelle installation d'app, ou un nouvel engagement, aux utilisateurs qui ont émis la recommandation.

L'attribution des invitations d'utilisateurs vous permet de :

* Analyser le coût et le ROI des invitations d'utilisateurs. Les invitations d'utilisateurs prennent l'espace publicitaire de votre application, qui pourrait être mis à profit pour générer des revenus publicitaires. Il peut donc être utile de savoir si les invitations d'utilisateurs donnent le meilleur ROI.
* Enregistrer des informations sur les utilisateurs qui recommandent le plus souvent votre application. Les utilisateurs qui invitent les autres à utiliser votre app sont des utilisateurs engagés très précieux, il peut donc être pertinent de les retargeter ou les relancer.

Vous pouvez également utiliser les données des liens pour :

* Personnaliser l'expérience du nouvel utilisateur. Par exemple en l'envoyant vers un contenu précis, ou en lui adressant un message de bienvenue personnalisé, comme «Bonjour Pierre ! Votre amie Marie vous propose de faire un jeu. Lancer la partie !»
* Récompenser les utilisateurs qui recommandent votre app.[En savoir plus](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

Les liens d'invitation que les utilisateurs partagent sont des liens personnalisés OneLink (URL courtes) qui sont générés par le SDK AppsFlyer intégré à votre app. Les paramètres de votre OneLink permettent aux utilisateurs qui reçoivent l'invitation d'être redirigés au bon endroit : l'app store concerné, votre application, ou sur une certaine page de votre application (via deep link ou différé).<Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">En savoir plus sur OneLink</Anchor>

<div id="flow" />

### Flux

Le flux est le suivant :

1. L'utilisateur A clique sur l'app pour la partager avec un ami. (L'utilisateur A a installé l'app et est bien connecté).
2. Le clic génère un lien qui contient un paramètre identifiant l'utilisateur A.
3. L'utilisateur A envoie le lien à l'utilisateur B par e-mail/WhatsApp/SMS, etc.
4. Si l'utilisateur B :
   * a déjà installé l'application, elle s'ouvre. L'utilisateur B peut être deep linké vers une certaine de l'application et/ou être récompensé.
   * n'a pas encore installé l'application, il est dirigé vers l'app store pour la télécharger.L'utilisateur B peut être deep linké en différé vers une certaine page de l'application à la première ouverture, et/ou l'utilisateur A peut être récompensé.
   * effectue un événement in-app, l'utilisateur A peut être récompensé.

<div id="viewing-data" />

## Consulter les données

Les données sur les invitations d'utilisateurs sont disponibles via les tableaux de bord et rapports AppsFlyer. Dans les tableaux de bord AppsFlyer, vous pouvez filtrer l'attribution des invitations d'utilisateurs par :

* **Source média** : invitations de l'app.
* **Canal** : tel que défini par le marketeur.
* **Campagne** : telle que définie par le marketeur.

Dans les rapports, la source média (paramètre `pid`) est envoyée par le SDK avec la valeur par défaut `af_app_invites`. 

<div id="procedures" />

## Procédures

**Pour créer des liens d'invitation d'utilisateurs** :

1. Créez un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink.</Anchor>
2. Déterminer les valeurs des paramètres du canal et de la campagne. Cf [Paramètres](/docs/user-invite-attribution#parameters).
3. Décidez comment vous souhaitez utiliser les liens. Les cas d'utilisation les plus courants sont les suivants :
   * Deep linker les nouveaux utilisateurs vers une certaine page de l'application.
   * Enregistrer les utilisateurs qui ont lancé l'invitation.
   * Récompenser les nouveaux utilisateurs.
4. Contactez vos développeurs Android et iOS pour décider des paramètres associés aux cas d'utilisation des liens que vous avez choisis. Cf [Paramètres](/docs/user-invite-attribution#parameters) disponibles.
5. Demandez au développeur <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">d'implémenter le deep linking</Anchor> (en utilisant le comportement souhaité des paramètres dans le code).
6. Demandez au développeur d'implémenter les invitations d'utilisateurs sur les plateformes suivantes :

   <Tabs>
   <Tab title="Android">

   Cf section [Invitation des utilisateurs sous Android](https://dev.appsflyer.com/hc/docs/dl_android_user_invite) du Dev Hub.

   </Tab>

   <Tab title="iOS">

   Cf section [Invitation des utilisateurs sous iOS](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite) du Dev Hub.

   </Tab>

   <Tab title="Unity">

   Cf section [Invitation des utilisateurs](https://dev.appsflyer.com/hc/docs/userinvite) du Dev Hub.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="Paramètres">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### Paramètres/valeurs à transmettre au développeur pour préparation du SDK

<table><thead><tr><th><span>Paramètre/valeur</span></th><th><span>Remarques</span></th><th><span>Enregistrer la valeur/le cas d'utilisation que le développeur doit implémenter</span></th></tr></thead><tbody><tr><td><span>ID du template OneLink</span></td><td><p>L'ID du template OneLink avec les paramètres de base qui définiront tous les liens d'invitation d'utilisateurs. Exemple : H5hv</p></td><td></td></tr><tr><td><span>Canal</span></td><td><p>Le nom du canal. Cela vous permettra de trier et afficher les attributions par canal dans l'IU AppsFlyer.</p></td><td></td></tr><tr><td><span>Campagne</span></td><td><p>Le nom de la campagne. Cela vous permettra de trier et afficher les attributions par campagne dans l'IU AppsFlyer.</p></td><td></td></tr><tr><td> <span>is_retargeting=true</span> </td><td><p>Ajouté si votre campagne a pour objectif le retargeting des utilisateurs existants.</p></td><td></td></tr><tr><td><span>deep_link_value</span></td><td><p>Paramètre à utiliser sur l'appareil de l'utilisateur invité pour lui offrir une expérience précise. Généralement, ce lien est utilisé pour <span>nommer la page vers laquelle les utilisateurs sont dirigés. Exemple : si votre app vend des fruits, vous pouvez deep linker les utilisateurs vers la page dédiée aux pommes.</span></p></td><td></td></tr><tr><td><span>deep_link_sub1</span></td><td rowspan="10"><p>Paramètre à utiliser sur l'appareil de l'utilisateur invité pour lui offrir une expérience précise. Comme deep_link_value est généralement utilisé pour envoyer les utilisateurs vers une certaine page, ce paramètre peut aussi être utilisé pour une autre fonctionnalité. Par exemple, pour ajouter une récompense ou une réduction, ou bien enregistrer l'utilisateur qui a émis la recommandation. </p></td><td></td></tr><tr><td><span>deep_link_sub2</span></td><td></td></tr><tr><td><span>deep_link_sub3</span></td><td></td></tr><tr><td><span>deep_link_sub4</span></td><td></td></tr><tr><td><span>deep_link_sub5</span></td><td></td></tr><tr><td><span>deep_link_sub6</span></td><td></td></tr><tr><td><span>deep_link_sub7</span></td><td></td></tr><tr><td><span>deep_link_sub8</span></td><td></td></tr><tr><td><span>deep_link_sub9</span></td><td></td></tr><tr><td><span>lien_profond_sub10</span></td><td></td></tr><tr><td><span>[Facultatif] pid</span></td><td><p>Par défaut, les liens que vous générez incluent la<span> source média (paramètre<code>pid</code> ) avec la valeur <code>af_app_invites</code></span>.</p><p><span>Pour modifier la valeur, votre développeur doit ajouter un paramètre personnalisé nommé <code>pid</code> contenant la valeur souhaitée. <strong>Remarque</strong> : sous Android, ne fonctionne que pour le SDK V6.4.2+.</span></p></td><td></td></tr><tr><td><span>Nom de marque</span></td><td><p>Le nom de domaine de la marque. Cela vous permettra de trier et afficher les attributions par domaine de marque dans l'IU AppsFlyer.</p></td><td></td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="Exemple">

Steph est marketeur et possède une application qui vend des fruits. Il veut créer un lien qui dirige les utilisateurs sur la page dédiée aux fruits, avec la possibilité d'acheter une certaine quantité de fruits.

Il veut envoyer ce lien dans une invitation d'utilisateur, et il souhaite que utilisateurs qui recommandent son app soient récompensés chaque fois que leur invitation génère l'installation de l'application et l'achat d'un fruit.

Pour que tout cela fonctionne, Steph envoie à son développeur la liste des paramètres et valeurs à utiliser lors de la mise en place des liens d'invitation d'utilisateurs :

| Paramètre | valeur | Remarques |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | Pour le deep linking utilisant la méthode UDL AppsFlyer. |
| deep\_link\_sub1 | promo\_code | Pour le deep linking utilisant la méthode UDL AppsFlyer. |
| deep\_link\_sub2 | referrer\_id | Pour la création de liens via le SDK. |
| param\_1 | referrer\_id | Pour l'événement in-app qui enregistre chaque achat. |
| Canal | mobile\_share | Pour l'attribution, et pour afficher les données dans AppsFlyer. |
| Campagne | summer\_sale | Pour l'attribution, et pour afficher les données dans AppsFlyer. |

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="record-user-invites-as-inapp-events" />

<Accordion title="Enregistrer les invitations d'utilisateurs comme des événements in-app">

L'enregistrement d'un événement in-app après l'envoi d'une invitation par un utilisateur vous permet d'identifier les utilisateurs qui font des recommandations, ainsi que les sources média qui vous permettent d'obtenir ces parrainages.

**Pour enregistrer un événement in-app d'invitation d'utilisateur** :

* Envoyez un <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#invite-af_invite">événement af\_invite</Anchor>. Le développeur doit l'installer en suivant les instructions de notre dev hub.

**Remarque** : vous pouvez ajouter d'autres paramètres à associer à l'événement. Choisissez les paramètres qui donneront plus d'infos sur l'événement et enrichiront les données. <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#configuration-des-événements-in-app">En savoir plus</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="Récompenser les parrains pour les installations découlant de leurs invitations">

**Pour récompenser un utilisateur pour une installation issue de son invitation :**

1. Vérifiez que l'ID du parrain est la valeur de l'un des [paramètres deep\_link\_sub1-10](/docs/user-invite-attribution#parameters).
2. Demandez aux développeurs de votre app <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">d'implémenter le deep linking</Anchor> (en utilisant le comportement associé au paramètre choisi dans le code).
3. Demandez à vos développeurs backend et développeurs d'apps de récupérer les ID de référent (depuis les rapports AppsFlyer), puis de les récompenser.

Exemple :

1. L'utilisateur A invite l'utilisateur B à installer votre application.
2. Lorsque l'utilisateur B lance l'app, celle-ci reçoit l'ID de référent de l'utilisateur A.
3. Votre backend récupère l'ID de référent dans les rapports AppsFlyer.
4. Dans votre backend, ajoutez l'ID de référent de l'utilisateur A à la liste des utilisateurs à récompenser
5. Lorsque l'utilisateur A lance l'application, vérifiez si son ID de référent figure dans la liste des utilisateurs à récompenser et, si c'est le cas, récompensez-le.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="Récompenser les parrains pour les actions des utilisateurs référés">

**Pour récompenser les parrains pour une invitation d'utilisateur qui génère un événement in-app précis :**

1. <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#configuration-des-événements-in-app">Créez l'événement in-app</Anchor> que vous souhaitez voir récompenser.
2. Indiquez au développeur d'ajouter un paramètre (par exemple, param\_1) à l'événement, la valeur étant l'ID du référent. **Remarque** : L'ID de référent est initialement enregistré lors de l'installation de l'app en utilisant le [paramètre](/docs/user-invite-attribution#parameters) que vous avez sélectionné (deep\_link\_sub1-10).
3. Demandez à vos développeurs backend et développeurs d'apps de récupérer les ID de référent (depuis les rapports AppsFlyer), puis de les récompenser.

Exemple :

1. L'utilisateur A invite l'utilisateur B à effectuer une action dans votre application.
2. Lorsque l'utilisateur B effectue l'action, un événement in-app est enregistré qui contient l'ID de référent de l'utilisateur A.
3. Votre backend récupère l'ID de référent dans les rapports AppsFlyer.
4. Dans votre backend, ajoutez l'ID de référent de l'utilisateur A à la liste des utilisateurs à récompenser
5. Lorsque l'utilisateur A lance l'application, vérifiez si son ID de référent figure dans la liste des utilisateurs à récompenser et, si c'est le cas, récompensez-le.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Description |
| --- | --- |
| Version du SDK | Vous devez avoir AppsFlyer SDK version 4.8.0+ et Unity SDK version 4.17.0+. |
| <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"> Page d'accueil des apps de réseaux sociaux</Anchor> | Les liens générés par les invitations d'utilisateurs ne peuvent pas implémenter les pages d'accueil des apps sociales. |
| Temps d'existence (TTL) | Le temps d'existence (TTL) par défaut des URL courtes OneLink créées via invitation d'utilisateur du SDK est de 60 jours. Il est prolongé de 60 jours à chaque fois que le lien est cliqué. |
| Tarification | Gratuit pour tous les forfaits de compte. |
| iOS 14+ | L'attribution des invitations utilisateur n'utilise pas l'IDFA. iOS 14 n'a donc aucune incidence sur celle-ci. |
| ID d'URL | L'ID de l'URL (ou ID du lien court) peut être modifié pour mettre en avant l'offre de votre campagne.Par exemple : https://myapp.onelink.me/abc123/pommes.L'ID d'URL peut comporter au maximum 50 caractères et peut inclure des lettres et des chiffres.Par défaut, il comporte 8 caractères.<br /><br />**Remarque** : Vous ne pouvez modifier l'ID de l'URL que si l'ID actuel n'est pas déjà utilisé. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=%C3%A0-propos-de-lattribution-des-invitations-dutilisateurs h_01H98E1CZ2AG8AW2H77SPPHFGR=%C3%A0-propos-de-lattribution-des-invitations-dutilisateurs flow=flux h_01H98E1CZ234MRBWDEYGZFCDRE=flux viewing-data=consulter-les-donn%C3%A9es h_01H98E1CZ23FEAS8JJC7FFTFXD=consulter-les-donn%C3%A9es procedures=proc%C3%A9dures h_01H98E1CZ2VBCG0RREERW8FNJE=proc%C3%A9dures h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=param%C3%A8tresvaleurs-%C3%A0-transmettre-au-d%C3%A9veloppeur-pour-pr%C3%A9paration-du-sdk h_01H98E1CZ2CANBK1T55DD103JB=param%C3%A8tresvaleurs-%C3%A0-transmettre-au-d%C3%A9veloppeur-pour-pr%C3%A9paration-du-sdk h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=informations-suppl%C3%A9mentaires h_01H98E1CZ28T2SJ3YNY8TNCAZY=informations-suppl%C3%A9mentaires h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
