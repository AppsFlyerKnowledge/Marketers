---
title: API d'événements serveur à serveur pour PBA (Web-S2S)
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2025-08-20T09:36:30Z'
  id: 360006997298
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360006997298
---
> **En bref :** Utilisez l'API d'événements Web Server-to-Server (Web-S2S) pour signaler à PBA les événements et les conversions qui ne sont pas signalés par le SDK Web.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/4694c3141c85a0dc62a29a3ace7b1986fa4cf7140cc5cdc532553b66dc100ff9-360007753757.jpg)](https://files.readme.io/4694c3141c85a0dc62a29a3ace7b1986fa4cf7140cc5cdc532553b66dc100ff9-360007753757.jpg)

## API d'événements de serveur à serveur Web pour PBA

L'API Web-S2S pour l'attribution basée sur les personnes complète le <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide">SDK Web</Anchor> en permettant aux spécialistes du marketing de signaler les événements qui se produisent sur leurs sites web mais qui ne sont pas couverts par le SDK Web. Par exemple, un visiteur du site web (un internaute) déclenche un paiement en ligne, traité par des systèmes en arrière-plan. Après traitement, l’arrière-plan signale l'événement à AppsFlyer via l'API S2S.

Événements envoyés par l'API S2S :

* sont enregistrés de la même manière que les événements signalés par le SDK Web
* sont inclus dans les tableaux de bord PBA s'ils sont définis comme des événements de conversion
* alimenter les données brutes PBA avec le *champ event\_source* réglé sur *web S2S*

## Instructions d'utilisation de l'API

Créez votre appel API à l'aide des sections suivantes.

| Non. | Élément | Remarques |
| --- | --- | --- |
| 1 | ID unique de l'utilisateur | <ul><li>Efforcez-vous de nous fournir le meilleur ID utilisateur unique disponible. Cela a un impact significatif sur l'analyse des données.</li><li>La bonne pratique consiste à envoyer customerUserId. S'il n'est pas disponible, il envoie afUserId, qui est l'ID du cookie du site web défini par WebSdk.</li><li>Lorsque vous associez votre ID d'utilisateur client<Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">(CUID)</Anchor> à [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid), un message setCuID() avec les deux ID est envoyé.</li></ul> |
| 2 | Horodatage | <ul><li>Nous supprimons votre horodatage si l'événement arrive en retard. Cela signifie que les événements dont l'horodatage est le lundi doivent arriver avant le mardi minuit UTC.</li><li>Les horodatages sont basés sur le système UTC. Si nécessaire, convertir l'heure locale en heure UTC avant de renseigner le paramètre.</li></ul> |
| 3 | Revenus et devises | Vous devez renseigner *eventRevenueCurrency* et *eventRevenue* même s'ils sont contenus dans eventValue. Nous les utilisons dans nos tableaux de bord. |

<div id="api-basics" />

<Accordion title="Principes de base de l'API">

La mise en œuvre de l'API nécessite les informations d'identification suivantes, disponibles dans le tableau de bord :

* ID de bundle (ou ID du bundle de marques)
* Clé dev web

**Pour obtenir les informations d'identification :**

1. Dans AppsFlyer, dans le menu supérieur, sélectionnez **Mes applications** > **Voir les bundles de marques**.  
   La liste des bundles s'affiche.
2. Copiez et enregistrez les données appropriées :
   * ***ID de bundle de marques***
   * ***Clé dev web***

#### Principes de base de l'API Web S2S

| Chemin | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId` : l'identifiant du bundle d'applications est-il disponible dans le tableau de bord ?</li><li>`method` soit l'un des éléments suivants :<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): envoi pour les événements d’arrière-plan à signaler</li><li>[setCuId :](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) envoyé lors de l'association de afUserId avec votre CUID</li></ul></li></ul> |
| --- | --- |
| Méthode HTTP | `POST` |
| Type de contenu accepté | `application/json` |
| Limitation de charge utile JSON | Taille de la charge utile JSON : maximum 1 Ko |
| Limitation de taux | Volume de limitation POST : 60 000 POST par minute. Pour augmenter la limite, contactez votre MSC. |
| Protocole TLS | <ul><li>TLS 1.2 ou supérieur</li><li><Anchor target="_blank" href="/marketers/fr/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">Chiffres pris en charge</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="Méthode setCuId">

| Nom de la méthode | setCuId |
| --- | --- |
| Cas d'utilisation | Pour l'association d'un CUID à un visiteur de votre site web. Par exemple, chaque fois que vous faites correspondre le site web `afUserId` avec l'ID de votre client. Cela permet à la PBA de faire correspondre des données provenant de différentes sources. Cette fonction est similaire à <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> sur le site web. |
| Chemin de la méthode | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Charge utile | La charge utile JSON se compose des paramètres énumérés ici. Tous les paramètres sont obligatoires.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

#### Exemple Curl setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="Méthode d'événement">

| Nom de la méthode | événement |
| --- | --- |
| Cas d'utilisation | Envoyer |
| Chemin de la méthode | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Informations détaillées | La section [Détails de la méthode d'événement](/docs/web-server-to-server-events-api-for-pba-web-s2s#détails-de-la-méthode-dévénement) de cet article contient des détails sur la charge utile, un exemple Curl, un exemple Python et des suggestions de test. |

</Accordion>

## Détails de la méthode d'événement

<div id="payload-parameters" />

<Accordion title="Paramètres de charge utile">

Les paramètres de la charge utile sont divisés en identifiants d'utilisateurs et en paramètres d'événements.

* ID utilisateur : Vous devez envoyer au moins un paramètre d'identification de l'utilisateur.
* Événement : Envoyer les paramètres obligatoires et les paramètres optionnels si nécessaire.

#### Paramètres d'identification de l'utilisateur (envoyer au moins un paramètre)

| Paramètre de l'ID utilisateur | Description |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | L'<Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">ID d'utilisateur client (CUID)</Anchor> est un identifiant unique que vous définissez.<ul><li>Utilisez le même identifiant pour les événements signalés à AppsFlyer par quelque moyen que ce soit. Cela signifie que le même identifiant est utilisé dans le SDK Web, le SDK mobile et les API S2S.</li><li><Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">ID utilisateur du client SDK Web</Anchor></li><li>Format : Chaîne</li><li>Exemple :`"customerUserId" : "663274"`</li><li>Remplit le champ de données brutes : `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | L'ID utilisateur unique attribué par le SDK Web à chaque utilisateur qui visite votre site web. Vous devrez transmettre la valeur du cookie à vos serveurs d’arrière-plan.<ul><li>Détails du cookie :<ul><li>Nom : afUserId</li><li>Valeur : attribuer cette valeur à *afUserId*</li><li>Domaine : website-domain</li></ul></li><li>Exemple : `"afUserId" : "unique_cookie_uuid"`</li><li>Remplit le champ de données brutes : `af_web_id`</li></ul> |

#### Paramètres d'événement

| Nom du paramètre | Obligatoire | Description |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | Oui | Remplir à l'aide de la [clé web dev](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) disponible sur le tableau de bord.<ul><li>Exemple :`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | Oui | Identifiant d'attribut d'événement à usage interne d'AppsFlyer. Toujours réglé sur *EVENT*.<ul><li>Exemple :`"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | Oui | <ul><li>Nous utilisons ce paramètre pour différencier les événements de conversion et de non-conversion à l'aide de la <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings#web-event-settings">liste de conversion des événements</Anchor> établie par le responsable marketing dans les paramètres PBA.</li><li>Veillez à l'alimenter avec des valeurs conformes à la logique de conversion de l'agent de marketing.</li><li>Format : chaîne.</li><li>Exemple :`"eventName" : "web_purchase"`</li><li>Remplit le champ de données brutes : `event_name`</li></ul> |
| <span id="timestamp"></span>Horodatage | Non | Heure à laquelle l'événement s'est produit, en millisecondes. Envoyer sous la forme d'un <Anchor target="_blank" href="https://www.unixtimestamp.com/">horodatage Unix</Anchor> de 13 chiffres.<ul><li>Si aucun horodatage n'est envoyé, l'heure est fixée en utilisant l'heure du serveur.</li><li>**Les événements qui arrivent en retard sont horodatés en fonction de l'heure actuelle du serveur.** L'arrivée tardive signifie l'arrivée après minuit UTC le jour suivant l'événement. Par exemple, un événement survenant le lundi **doit être** traité avant le mardi à minuit UTC.</li><li>Les événements dont l'heure se situe dans le futur (par rapport à l'heure actuelle du serveur) sont horodatés avec l'heure du serveur.</li><li>Format : Int</li><li>Exemple :`"timestamp" : 1584835200123`</li><li>Remplit le champ de données brutes : `event_time`</li></ul> |
| <span id="eventvalue"></span>Valeur de l'événement | Non | Carte des paramètres de l’événement décrivant l’événement. Utilisez ce paramètre pour envoyer des évènements rich in-app, tels que la référence SKU du produit et le prix de l’article.<ul><li>**Remarque relative aux revenus :** Vous pouvez renseigner ce paramètre avec les détails du revenu. Vous devez également renseigner *eventRevenue* et *eventRevenueCurrency*.</li></ul><ul><li>Format : JSON</li><li>Exemple : Pour envoyer le SKU ABC123, d'une couleur bleue et d'un prix unitaire de 3,99 $, définissez eventValue ainsi :<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>**Limitation :** 1000 caractères. Ne dépassez pas cette limite, sinon la valeur sera tronquée.</li><li>Remplit le champ de données brutes : `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | Non | Code devise d'un fait générateur de recettes, à savoir un code devise <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> à trois caractères.<ul><li>Par défaut : USD</li><li>Format : chaîne</li><li>Exemple :  `"eventRevenueCurrency" : "EUR"`</li><li>Remplit le champ de données brutes : `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | Non | Revenus (valeur monétaire) affectés à un événement.<br /><br />**Important !** Si les recettes sont déclarées dans *eventValue,* elles sont également déclarées dans *eventRevenue* et remplissent eventRevenueCurrency.<ul><li>Les valeurs négatives sont autorisées. Par exemple, un remboursement.</li><li>Format : Float</li><li>Exemple de valeurs : `1``1.2``1234.20``-1234.20`</li><li>Remplit le champ de données brutes : `event_revenue`</li></ul> |
| <span id="eventcategory"></span>eventCategory | Non | Ce paramètre est obsolète et sera supprimé du système à une date ultérieure. Utilisez plutôt eventValue. |
| <span id="eventlabel"></span>eventLabel | Non | Ce paramètre est obsolète et sera supprimé du système à une date ultérieure. Utilisez plutôt eventValue. |
| <span id="referrer"></span>Référent | Non | Référent HTTP<ul><li>Format : chaîne</li><li>Exemple :`"referrer" : "https://www.google.com/"`</li><li>Remplit le champ de données brutes : `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | Non | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">Requête de l'agent utilisateur</Anchor> envoyée par le navigateur au serveur.<ul><li>Dans la mesure du possible, envoyez cette valeur, car elle permet de déterminer le type d'appareil.</li><li>Format : chaîne</li><li>Exemple : `"userAgent" : "Chrome/80.0.3987"`</li><li>Remplit le champ de données brutes : `user_agent`</li></ul> |
| <span id="ip"></span>ip | Non | Adresse IP de l'utilisateur<ul><li>Dans la mesure du possible, envoyer la valeur de ce champ. Il permet de déterminer la <Anchor target="_blank" href="/marketers/fr/docs/determine-user-location">géolocalisation</Anchor> de l'utilisateur.</li></ul><ul><li>Format : chaîne</li><li>Exemple :`"ip": "192.0.2.1"`</li><li>Remplit le champ de données brutes : `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Exemple Curl">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,

		"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}

}'
```

</Accordion>

<div id="python-example" />

<Accordion title="Exemple Python">

```python
''' using the requests python package, install using pip install requests  '''
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Accordion>

<div id="testing" />

<Accordion title="Test">

À des fins de test, envoyez plusieurs événements comme suit :

1. Envoyer un événement.
2. Assurez-vous que vous obtenez un code de retour 200 OK. Si ce n'est pas le cas, prenez des mesures correctives à l'aide des codes de retour et des messages d'erreur.
3. Attendez plusieurs heures après minuit UTC pour voir l'événement reporté dans les données brutes du PBA. Vous devez attendre, car les données PBA sont traitées une fois par jour.

</Accordion>

## Informations supplémentaires

<div id="getting-the-web-dev-key" />

<Accordion title="Obtenir la clé Web Dev">

**Pour obtenir la clé de dev Web :**

1. Dans AppsFlyer, allez dans la section ***Mes applications.***
2. Cliquez sur Voir le bundle de marques.

   [![GetWebDevKeyPba_us-en.pn](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)
3. Copiez la ***clé de développement web requise*.**

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Extraction de afUserID du SDK Web">

* Le `afUserId` est un identifiant unique, défini par le SDK Web lorsqu'un utilisateur visite votre site pour la première fois.
* Si vous avez besoin de `afUserId`, utilisez l'une des méthodes suivantes.

#### **Obtenir afUserId à partir de l'en-tête du cookie HTTP**

* `afUserId` est envoyé par le navigateur des visiteurs lorsqu'ils visitent votre site.
* L'extraire de l'en-tête du cookie HTTP si nécessaire.

#### **Affichage de afUserId dans le navigateur du visiteur**

* Afficher `afUserId` dans le navigateur du visiteur, à des fins de dépannage et de débogage.
* Pour qu'il soit disponible, le visiteur doit d'abord avoir consulté au moins une fois une page contenant le SDK Web.
* Le cookie contenant `afUserId` est un cookie first party lié à votre domaine.
* La procédure qui suit a été préparée à l'aide de Chrome 81. Il peut y avoir des différences entre les navigateurs et les systèmes d'exploitation.

**Pour obtenir l'afUserId du navigateur du visiteur :**

1. Dans votre navigateur, allez sur votre site web.
2. Cliquez avec le bouton droit de la souris et sélectionnez ***Inspecter***La fenêtre d'inspection des éléments du navigateur s'ouvre.

   [![S2S_inspect.jpg](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)
3. Aller à la (A) ***Application*** (A).
4. Dans le menu latéral, (B) développez Cookies.
5. Sélectionnez votre site web. S’il ne s'affiche pas, actualisez le navigateur.
6. Dans le ***filtre*** (C) entrez `afUserId`  
   La valeur de afUserID s'affiche.

</Accordion>

<div id="response-codes" />

<Accordion title="Codes de réponse">

| Code de réponse | Message | Gestion |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Pas de résultat | <ul><li>Vérifier le point de terminaison</li><li>Vérifier que l'identifiant de bundle est correct</li></ul> |
| 400 | Demande incorrecte | <ul><li>Il y a une erreur dans le JSON. Voir le message d'erreur pour plus de détails.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Dépannage">

* Symptôme : les codes de retour HTTP ne sont pas renvoyés  
  Solution : liste des serveurs autorisés AppsFlyer

</Accordion>

<div id="release-notes" />

<Accordion title="Notes de mise à jour">

<table><caption>Notes de mise à jour du SDK Web</caption><thead><tr><th>Date </th><th>Version du point de terminaison\*</th><th>Remarques</th></tr></thead><tbody><tr><td>2020-05-12</td><td>1</td><td> Version initiale</td></tr><tr><td>2020-05-24</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* Le numéro de version correspond au numéro de version du point de terminaison. <code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=api-d%C3%A9v%C3%A9nements-de-serveur-%C3%A0-serveur-web-pour-pba h_01HKW2YAW4HHYK27F41HC3B24Y=api-d%C3%A9v%C3%A9nements-de-serveur-%C3%A0-serveur-web-pour-pba api-use-instructions=instructions-dutilisation-de-lapi h_01HKW2YAW4DCESP3MNY9D4GTFK=instructions-dutilisation-de-lapi h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=principes-de-base-de-lapi-web-s2s h_01HKW2YAW4XDKZ3YGAHAP3AG2T=principes-de-base-de-lapi-web-s2s h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=exemple-curl-setcuid h_01HKW2YAW5SJFKGTNRGRKN6NCJ=exemple-curl-setcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=d%C3%A9tails-de-la-m%C3%A9thode-d%C3%A9v%C3%A9nement h_01HKW2YAW53H43SCYTDXAYBDHX=d%C3%A9tails-de-la-m%C3%A9thode-d%C3%A9v%C3%A9nement h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=param%C3%A8tres-didentification-de-lutilisateur-envoyer-au-moins-un-param%C3%A8tre h_01HKW2YAW5RR4Q2PCWC9717ACG=param%C3%A8tres-didentification-de-lutilisateur-envoyer-au-moins-un-param%C3%A8tre event-parameters=param%C3%A8tres-d%C3%A9v%C3%A9nement h_01HKW2YAW5G46ZV4Z0CYEWB011=param%C3%A8tres-d%C3%A9v%C3%A9nement h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=informations-suppl%C3%A9mentaires h_01HKW2YAW5D4N3SYA625F10YFW=informations-suppl%C3%A9mentaires h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=obtenir-afuserid-%C3%A0-partir-de-len-t%C3%AAte-du-cookie-http h_01HKW2YAW5FK04C3AWCXGP1XAW=obtenir-afuserid-%C3%A0-partir-de-len-t%C3%AAte-du-cookie-http viewing-afuserid-in-the-visitors-browser=affichage-de-afuserid-dans-le-navigateur-du-visiteur h_01HKW2YAW5CT2WZ229KJD2FWYK=affichage-de-afuserid-dans-le-navigateur-du-visiteur h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
