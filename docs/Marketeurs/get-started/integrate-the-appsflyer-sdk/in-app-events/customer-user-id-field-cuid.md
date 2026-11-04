---
title: Champ ID utilisateur du client (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2023-11-30T11:59:02Z'
  id: 207032016
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/207032016
---
> **En bref** : le CUID vous permet de regrouper les événements d'un même utilisateur sur plusieurs appareils, sources média ou canaux.

<div id="what-is-cuid" />

## **Qu'est-ce qu'un CUID ?**

Le Customer User ID (CUID) **est un**   
identifiant utilisateur unique.Il est généralement produit et défini par le propriétaire de l'app au moment de l'inscription de l'utilisateur.Le CUID permet aux propriétaires d'app de suivre le parcours d'un utilisateur sur différents appareils.

<div id="example" />

> 📄 **Exemple**
>
> Un utilisateur possédant plusieurs appareils a le même CUID dans une app. Chaque fois que l'utilisateur effectue un événement sur un appareil mobile ou un ordinateur, l'événement est capturé avec le CUID. Cela permet à l'annonceur de combiner les données des appareils pour obtenir une vision globale des actions de l'utilisateur.
>
> Quelques cas d'utilisation :
>
> * Les achats in-app effectués par le même utilisateur sur différents appareils (mobile, tablette, TV, ordinateur) peuvent être regroupés en une seule vue.
> * Les performances de l'utilisateur pour un jeu installé sur plusieurs plateformes (ordinateur, mobile ou TV) peuvent être partagées entre les plateformes pour permettre au joueur de passer facilement d'une plateforme à l'autre.

<div id="setting-the-cuid" />

## **Paramétrer le CUID**

Il est recommandé de définir le CUID le plus tôt possible dans le flux d'initialisation du SDK afin que le plus grand nombre d'événements reçoivent une association CUID.

<Tabs>
<Tab title="Android natif">

Une fois que le CUID est disponible, vous pouvez le définir en appelant  `setCustomerUserID` . Le CUID peut uniquement être associé à des événements in-app se produisant après qu'il a été défini. Par conséquent, l'événement d'installation n'est pas associé au CUID lorsque `start` est appelé avant `setCustomerUserID`.

<div id="associate-the-cuid-with-the-install-event" />

### **Associer le CUID à l'événement d'installation**

S'il est important pour vous d'associer l'événement d'installation au CUID, vous devez procéder à la configuration avant d'appeler `start`.

**Important :** n'oubliez pas que le fait de configurer le CUID avant `start` peut empêcher le SDK d'envoyer l'événement d'installation et donc, bloquer l'attribution. Cela peut se produire, par exemple, lorsque l'utilisateur lance l'app pour la première fois et la quitte avant que le SDK ne puisse définir le CUID.

Dans Android, la méthode `start` et la configuration du CUID peuvent être exécutées depuis la classe globale `Application` ou une quelconque classe `Activity` selon la manière dont l'app a été implémentée. Pour plus d'informations, consultez <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#sélectionner-la-classe-dans-laquelle-démarrer-le-sdk">Choisir la classe pour démarrer le SDK.</Anchor>

<div id="if-the-sdk-starts-in-the-application-class" />

#### Si le SDK démarre dans la classe Application

Si vous souhaitez associer le CUID à l'événement *install* lorsque vous démarrez depuis la classe globale `Application`, pensez à retarder l'envoi de l'événement d'installation avec la méthode `waitForCustomerUserId`. Cette méthode met le SDK en attente jusqu'à ce que le CUID soit défini.

Remarque : Si le paramétrage du CUID échoue, le SDK reste en mode d'attente et n'envoie aucun événement.

<div id="if-the-sdk-starts-in-an-activity-class" />

#### Si le SDK démarre dans une classe Activity

Si vous souhaitez associer le CUID à l'événement d'installation lorsque vous démarrez avec une classe `Activity` , vous ne devez pas retarder l'envoi de l'événement d'installation. Il suffit d'appeler `setCustomerUserId` avant d'appeler `start`.

<div id="developer-instructions" />

#### Instructions pour les développeurs

Transmettez au développeur les éléments suivants :

* Utilisez `waitForCustomerUserId`  si le SDK démarre dans la classe globale `Application`
* Liens pour les développeurs :
  * Pour associer le CUID à l'événement d'installation, [suivez ce lien](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event).

</Tab>

<Tab title="">

Passez par la méthode `customerUserId` pour définir le CUID. L'emplacement de `CustomerUserId`  par rapport à la méthode `start` détermine quels événements peuvent être associés au CUID.

* Si `customerUserId` est appelé avant `start`, le CUID est associé à l'installation et aux événements in-app qui suivent
* S'il est appelé après `start`, le CUID n'est associé qu'aux événements enregistrés après que le CUID a été défini.

<div id="developer-instructions-1" />

#### Instructions pour les développeurs

Demandez à votre développeur de se référer à la rubrique [Définir l'ID utilisateur du client](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id) dans le Dev Hub.

</Tab>

<Tab title="iOS natif">

<div id="developer-instructions-2" />

#### Instructions pour les développeurs

Demandez à votre développeur de se référer à la rubrique [Définir l'ID utilisateur du client](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id) dans le Dev Hub.

</Tab>

<Tab title="UnityReact natif">

<div id="developer-instructions-3" />

#### Instructions pour les développeurs

Référez votre développeur à la référence d'API [setCustomerUserId](https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid) dans le Dev Hub.

</Tab>
</Tabs>

<div id="cuid-and-privacy" />

## **CUID et confidentialité**

AppsFlyer respecte la vie privée de vos utilisateurs et [n'autorise donc ni la collecte ni le transfert d'informations personnelles identifiables depuis la plateforme AppsFlyer.](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

Pour sécuriser la confidentialité de vos utilisateurs, il est interdit de concevoir le CUID en y incluant la moindre information qui identifie directement l'utilisateur. Il s'agit notamment des numéros de sécurité sociale ou d'identification nationale.

En outre, si le CUID défini contient l'e-mail ou le numéro de téléphone d'un utilisateur, ces informations doivent toujours être cryptées lors de leur transfert vers AppsFlyer. Il est interdit d'envoyer à AppsFlyer des CUID non cryptés contenant des données personnelles.

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#rapports-de-parcours-utilisateur">Rapports sur le parcours de l'utilisateur</Anchor> (pour en savoir plus sur le CUID dans les rapports de données brutes)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Les conseils de Google pour ne pas transmettre d'informations confidentielles</Anchor>

<div data-zendesk-anchors="what-is-cuid=quest-ce-quun-cuid h_01HAJ00DVHRSDBS4FFKM16JFER=quest-ce-quun-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=exemple setting-the-cuid=param%C3%A9trer-le-cuid h_01HAJ00DVHDGM133A72HD5JXER=param%C3%A9trer-le-cuid associate-the-cuid-with-the-install-event=associer-le-cuid-%C3%A0-l%C3%A9v%C3%A9nement-dinstallation h_01HAJ00DVHDE9V2MT6JQF8SAH3=associer-le-cuid-%C3%A0-l%C3%A9v%C3%A9nement-dinstallation if-the-sdk-starts-in-the-application-class=si-le-sdk-d%C3%A9marre-dans-la-classe-application h_01HAJ00DVH746B6YJVF70PMZJ8=si-le-sdk-d%C3%A9marre-dans-la-classe-application if-the-sdk-starts-in-an-activity-class=si-le-sdk-d%C3%A9marre-dans-une-classe-activity h_01HAJ00DVHYZBER40RJH0GM8KF=si-le-sdk-d%C3%A9marre-dans-une-classe-activity developer-instructions-android=instructions-pour-les-d%C3%A9veloppeurs h_01HAJ00DVHZBZCRA1VGYJY44VY=instructions-pour-les-d%C3%A9veloppeurs developer-instructions::31dbab4b=instructions-pour-les-d%C3%A9veloppeurs h_01HAJ00DVH2RV902D6G224A4QY=instructions-pour-les-d%C3%A9veloppeurs developer-instructions-unity=instructions-pour-les-d%C3%A9veloppeurs h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=instructions-pour-les-d%C3%A9veloppeurs developer-instructions-react=instructions-pour-les-d%C3%A9veloppeurs cuid-and-privacy=cuid-et-confidentialit%C3%A9 h_01HAJ00DVH4987JGZZVDA1NB29=cuid-et-confidentialit%C3%A9 h_01HE7RXTEPQAWV03276TDEPG0V=%C3%A0-consulter-%C3%A9galement" />
