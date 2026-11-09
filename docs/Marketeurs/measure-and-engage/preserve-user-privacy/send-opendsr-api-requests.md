---
title: API OpenDSR
metadata:
  keywords:
    - Advertisers
    - GDPR
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2023-12-04T11:41:05Z'
  id: 11332840660625
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/11332840660625
---
> **En bref :** cet article est destiné aux clients AppsFlyer (également appelés annonceurs ou propriétaires d'app) qui utilisent la plateforme AppsFlyer pour enregistrer l'utilisation et l'attribution de l'app. Les propriétaires d'app implémentent l'API OpenDSR (Data Subject Request) pour se conformer aux lois de protection des données applicables comme le RGPD (Europe), la CCPA (Californie), la LGPD (Brésil) et le PDPA (Thaïlande).

Un message de nos avocats : *rien de ce qui est énoncé ici n'a valeur de conseil juridique. Les éléments ne sont fournis qu'à titre d'information. Vous devez travailler en étroite collaboration avec des conseillers juridiques ou assimilés pour déterminer avec précision comment le RGPD, la CCPA ou toute autre loi doit s'appliquer à votre cas.*La relation de confidentialité qui existe entre AppsFlyer et vous est régie par la <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">politique de confidentialité des services AppsFlyer.</Anchor> Pour toute question relative à la présente Politique de confidentialité des services ou pour contacter notre délégué à la protection des données, veuillez nous envoyer un e-mail à [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Aux fins de l'article 27 du Règlement général sur la protection des données, le représentant d'AppsFlyer au sein de l'UE est AppsFlyer Germany GmbH Schönhauser Allee 180, 10119, Berlin, Allemagne (contact : [privacy@appsflyer.com](mailto:privacy@appsflyer.com), +49-30-166373500).

<div id="privacy-regulations" />

## Politiques de confidentialité

Dans cet article, les références aux règles de confidentialité incluent les réglementations détaillées dans le tableau suivant.

| Réglementation | Logo | Description |
| --- | --- | --- |
| RGPD | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | Le Règlement Général sur la Protection des Données est une réglementation de l'UE relative à la protection des données et à la vie privée des citoyens de l'Union Européenne |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | California Consumer Privacy Act |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Loi sur la protection des renseignements personnelles (PDPA) |

Chacun des termes "règlement sur la protection de la vie privée", "RGPD", "CCPA", "LGPD" et "PDPA" est utilisé indifféremment dans cet article.

<div id="the-opendsr-initiative" />

### L'initiative OpenDSR

Pour répondre aux demandes des personnes concernées et les gérer, conformément aux règles de confidentialité, AppsFlyer, en collaboration avec mParticle, Amplitude et Braze, ont lancé le protocole OpenDSR (anciennement connu sous le nom de OpenGDPR).

OpenDSR est un cadre open-source facilitant la coopération entre les entreprises technologiques pour l'utilisation équitable et transparente des données des consommateurs.Il permet aux fournisseurs de prendre des mesures de confidentialité des données sur des **systèmes multiples** pour traiter et stocker les données client.

En <Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">savoir plus sur l'initiative OpenDSR</Anchor>.

<div id="definitions" />

### Définitions

| Conditions DSR | Termes Appsflyer | Description |
| --- | --- | --- |
| Personne concernée | Utilisateur d'app ou utilisateur final | L'utilisateur d'app dont les données sont collectées |
| Responsable du traitement des données | Propriétaire d'app ou annonceur | Le propriétaire d'app détermine le but et les moyens par lesquels les données personnelles sont traitées. |
| Processeur de données | AppsFlyer et ses partenaires | AppsFlyer et ses partenaires traitent les données personnelles au nom du responsable du traitement des données |

<div id="dsr-requirements" />

### Exigences DSR

DSR détaille les droits obligatoires de la personne concernée par les données, que le responsable des données doit respecter.Pour servir l'API, ces droits sont traduits en types de demande. Les informations suivantes expliquent comment AppsFlyer traite les différents types de demande.

| **Type de demande**<br /><br />**(Droit)** | **Définition du RGPD** | Traitement de la demande par AppsFlyer |
| --- | --- | --- |
| **Accès** | <ul><li>S'ils le souhaitent, les utilisateurs d'une app ont le droit de savoir si, pourquoi et pendant combien de temps le propriétaire de l'app traitera leurs données.</li><li>Si les données sont partagées avec des tiers, comme AppsFlyer, les utilisateurs d'une app ont le droit de savoir qui sont ces tiers.</li><li>Le droit de savoir quelles catégories de données sont traitées.</li><li>En cas de traitement automatisé, si ce dernier a un effet significatif sur celles-ci.</li></ul> | Les propriétaires de l'app reçoivent une copie du traitement des données personnelles de l'utilisateur de l'app. |
| **Portabilité** | L'utilisateur de l'app doit recevoir toutes ses données personnelles sous un format structuré, communément utilisé et lisible par une machine, comme un fichier CSV. | Le propriétaire de l'app reçoit une copie du traitement des données personnelles de l'utilisateur de l'app. |
| **Rectification** | Permet aux utilisateurs d'app de corriger leurs données s'ils voient qu'elles sont inexactes ou erronées.Les propriétaires d'app sont tenus d'effacer ou corriger les données inexactes ou incomplètes. | <ul><li>AppsFlyer supprime les données de l'utilisateur de l'app qui ont enregistrées avant la date de la demande de *rectification*.</li><li>Les données qui sont reçues après cette date sont enregistrées par AppsFlyer.</li></ul> |
| **Effacement** | Le droit à l'effacement oblige les propriétaires d'app à supprimer toutes les données personnelles dans un délai de 14 jours après réception de la demande. | Les données sont effacées |

<div id="appsflyer-gdpr-requests-api" />

## API de demande RGPD d'AppsFlyer

Pour implémenter la conformité RGPD, utilisez l'API de demande RGPD, comme décrit dans ce chapitre.

* **Demande RGPD -** Effectuer l'un des types de demande ci-dessus: accès, portabilité, effacement, rectification.
* **Demande d'état** - Interroger l'état actuel d'une demande RGPD
* **Demande de découverte** : Se renseigner sur la version de l'API et le format de données pris en charge
* **Annulation** : annuler une demande RGPD pendant sa phase ***traitement en cours***.

Les propriétaires d'apps doivent apporter des modifications dans l'IU de leur app avant que les utilisateurs de l'app ne puissent remplir une demande. Notez que chaque demande RGPD ne concerne qu'un utilisateur à la fois.

<Accordion title="1. Demande RGPD">

<div id="gdpr-request-flow" />

### Flux de demande RGPD

Les types de demande RGPD, que ce soit l'accès, la portabilité, l'effacement ou la rectification, suivent la même procédure :

1. **Un utilisateur de l'app** soumet une demande.
2. **Le propriétaire de l'app** élabore la demande RGPD (voir ci-dessous) puis l'envoie à AppsFlyer.
3. **AppsFlyer** reçoit la demande et répond par un "201 OK" pour les demandes valides.
4. Durant les 48 heures suivantes, la demande est mise dans la file d'attente, son état est ***pending***. L'utilisateur de l'app peut encore annuler la demande.
5. Les 48 heures écoulées, l'état de la demande passe à ***in\_progress.*** AppsFlyer envoie un postback de ***modification de statut***.La demande ne peut alors plus être annulée.
6. Dans un délai de 14 jours (voir note ci-dessous), AppsFlyer répond à la demande, le statut de la demande est mis à jour et passe sur ***terminé***.AppsFlyer envoie un postback de modification de statut.
   * Dans le cas d'un *effacement* ou d'une *rectification*, les données de l'utilisateur de l'app sont supprimées.
   * Dans le cas d'une *portabilité* ou *d'un accès,* les données de l'utilisateur de l'app sont accessibles dans la section **RGPD** du tableau de bord AppsFlyer, ou bien via l'API de demande (voir ci-dessous).

   **Remarque :** Cette période de 14 jours commence une fois que la période d'***attente de*** 48 heures a pris fin. Ainsi, la période totale pour répondre à la demande est de 16 jours après que le propriétaire de l'app a soumis la demande à AppsFlyer.

<div id="gdpr-request-format" />

### Format de la demande RGPD

Une API de demande RGPD peut être envoyée via HTTP POST au point de terminaison suivant :

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Pour l'autorisation API, utilisez le même jeton API V2 que pour l'API Pull. Un utilisateur admin peut <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens#récupération-des-jetons-dapi">récupérer le jeton</Anchor> à partir de la page du jeton API dans le tableau de bord. Ajoutez le jeton dans l'en-tête de la requête comme suit : `'Authorization': 'Bearer %AuthTokenV2%'`

<div id="parameters" />

#### Paramètres

<table><thead><tr><th><strong>Nom de la propriété</strong></th><th><strong>Obligatoire</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Oui</td><td>Chaîne UUID v4. Générée par le responsable du traitement au moment de la soumission de la demande à un processeur. Elle peut ensuite être utilisée pour vérifier l'état de la demande, la mettre à jour ou l'annuler.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Oui</td><td><p>Valeur de chaîne représentant le type de demande RGPD.  Valeurs prises en charge :</p><ul><li>effacement</li><li>portabilité</li><li>Accès</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Oui</td><td><ul><li>Un ensemble de d'éléments d'identification permettant de définir l'identité du demandeur (voir ci-dessous).</li><li>Chaque demande peut contenir une seule identité.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Oui</td><td><ul><li>Chaîne de date RFC 3339 indiquant l'heure de la demande d'origine par la personne sujette.</li><li>Horodateurs en UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Oui</td><td><p>Chaîne représentant l'application mobile à laquelle cette�demande est étendue</p><p><strong>Exemples</strong> :</p><ul><li> iOS : id123456789</li><li> <strong>Android</strong> : com.example, com.publishers.name</li><li> <strong>Android hors store</strong> : com.publisher.name-channel<br/> <strong>Remarque</strong> Dans certains cas, les propriétaires d'app enregistrent l'attribution hors store à l'aide du nom Android Google Play. Le cas échéant, utilisez le nom habituel de l'app, tel qu'il s'affiche dans le tableau de bord.</li></ul></td></tr><tr><td><strong><strong>api_version</strong></strong></td><td>Non</td><td>Chaîne de version représentant la version souhaitée de l'API de demandes RGPD</td></tr><tr><td><strong>status_callback_urls</strong> </td><td>Non, mais recommandé</td><td><ul><li>Ensemble de 3 points de terminaison maxi pour les callbacks d'état à envoyer lors des changements d'état de demande suivants.</li><li>Seuls<span> les points de terminaison HTTPS sont pris en charge.</span> </li><li><span>Les URL non valides sont rejetées.</span></li></ul></td></tr><tr><td rowspan="2"> <strong>platform</strong> </td><td>Non</td><td><p>Value est l'une des plateformes DSR prises en charge :<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code></p></td></tr><tr><td>Oui</td><td><p>Pour une demande de plateforme CTV, PC ou Console, inclure l'une des plateformes suivantes : </p><p><span> </span><code>nativepc</code><span>, </span><code>playstation</code><span>, </span><code>roku</code><span>, </span><code>steam</code><span>, </span><code>webos</code><span>, </span><br/><code>vidaa</code><span>,</span><code>tizen</code><span>, </span><code>smartcast</code><span>, </span><code>chatgpt</code><span>, </span><code>battlenet</code><span>, </span><br/><code>quest</code><span>, </span><code>switch</code><span>, </span><code>xbox</code><span>, </span><code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Éléments Subject\_identities

| Type d'élément | **Obligatoire** | **Description** |
| --- | --- | --- |
| identity\_type | Oui | <ul><li>Le type d'identité de format chaîne pour les plateformes `android`, `ios`, `web`, `windowsphone` sera choisi parmi les suivants :<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li></ul></li></ul><ul><li>Le type d'identité au format chaîne de caractères pour les plateformes `CTV`, `PC` et `Console` :<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Exemple : `android_advertising_id`</li></ul> |
| identity\_value | Oui | <ul><li>Format : chaîne</li><li>Exemple : "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | Oui | <ul><li>La méthode utilisée pour encoder identity\_value : `raw` est la seule prise en charge :</li><li>Example : "raw"</li></ul> |

<div id="zd-gdpr-erasure-request-code-example" />

<div id="example-gdpr-erasure-request" />

### Exemple : demande d'effacement RGPD

**Exemple de demande d'effacement pour les plateformes `android`, `ios`, `web`, `windowsphone` :**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \  
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '{ 
 "subject_request_id":"f4e5a271-f25e-4107-b681-************",
 "subject_request_type":"erasure",
 "submitted_time":"2020-07-05T10:00:00Z",
 "platform": "android",
 "subject_identities":[ 
  { 
   "identity_type":"android_advertising_id",
   "identity_value":"55*****-****-****-************",
   "identity_format":"raw"
  }
 ],
 "api_version":"0.1",
 "property_id":"com.*********.*******.********",
  "status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",  
  ]
}'
```

**Exemple de demande de suppression pour les `plateformes CTV`, `PC` et `Console`:**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \N-
--header 'Accept : application/json' \N-
--header 'Content-Type : application/json' \N- --header 'Content-Type : application/json' \N- --header 'Authorization'.  
--header 'Authorization : Bearer %AuthTokenv2% \N-
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
" subject_request_type":"erasure",
" submitted_time":"2020-07-05T10:00:00Z",
" subject_identities":[ 
 { 
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
" api_version":"0.1",
"property_id":"app-id",
" platform": "roku",
" status_callback_urls":[ 
 " https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

<div id="gdpr-erasure-request-code-example" />

### Exemple de code de demande RGPD d'effacement

<Tabs>
<Tab title="Java">

```java
/* 
using the okhttp package install from maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */

import okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null,  "" +
  "{\r\n\"subject_request_id\": \"\"," +
  "\r\n\"subject_request_type\": \"erasure\"," +
  "\r\n\"platform\": \"android\"," +
  "\r\n\"submitted_time\": \"2018-11-02T15:00:00Z\"," +
  "\r\n\"subject_identities\": [\r\n" +
  "{\r\n\"identity_type\": \"android_advertising_id\"," +
  "\r\n\"identity_value\": \"\"," +
  "\r\n\"identity_format\": \"raw\"\r\n}" +
   "\r\n]," +
   "\r\n\"property_id\": \"com.example.application\"}");

  Request request = new Request.Builder()
  .url("https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/opendsr_requests")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Accept", "application/json")
  .addHeader("Authorization: Bearer", "")
  .build();

    try {
   Response response = client.newCall(request).execute();
   System.out.println(response.code());
   System.out.println(response.body().string());
   System.exit(0);
  } catch (IOException e) {
   e.printStackTrace();
   System.exit(1);
  }
 }
}
```

</Tab>

<Tab title="Python">

```python
""" using the requests python package, 
install using pip install requests """

import requests
import json
headers = {
 "Content-Type": "application/json",
 "Accept": "application/json",
 "Authorization: Bearer": ""
}

body = {
 "subject_request_id": "", 
 "subject_request_type": "erasure", 
 "submitted_time": "2018-10-02T15:00:00Z",
 "platform": "android", 
 "subject_identities": [
  { "identity_type": "android_advertising_id", 
   "identity_value": "", 
   "identity_format": "raw" }
  ], 
 "property_id": "com.example.application" 
} 
body = json.dumps(body) 
res = requests.request("POST", 
"https://hq1.appsflyer.com/gdpr/opengdpr_requests", 
headers=headers, data=body, params=params) 
print(res.text)
```

</Tab>

<Tab title="Node.js">

```javascript
/* using the request npm package, 
install using npm install request */

var request = require("request");
var options = { method: 'POST',
 url: 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests',
 headers: 
 { Accept: 'application/json',
  'Content-Type': 'application/json',
  'Authorization: Bearer': '' },
 body:
 { subject_request_id: '',
  subject_request_type: 'erasure',
  submitted_time: '2018-10-02T15:00:00Z',
  platform: 'android',
  subject_identities: 
  [ { identity_type: 'android_advertising_id',
   identity_value: '',
   identity_format: 'raw' } ],
 property_id: 'com.example.application'
 },
 json: true };
request(options, function (error, response, body) {
 if (error) throw new Error(error);

 console.log(body);
});
```

</Tab>

<Tab title="C#">

```csharp
using System;
 using RestSharp;
 namespace CS
 {
  class Gdpr
  {
   static void Main(string[] args)
   {
 		var url = "https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests";
   var client = new RestClient(url);
   var request = new RestRequest(Method.POST);
   request.AddHeader("Content-Type", "application/json");
   request.AddHeader("Accept", "application/json");
   request.AddHeader("Authorization: Bearer", "")
   var body = "{\r\n\"subject_request_id\": \"\"," + 
    "\r\n \"subject_request_type\": \"erasure\"," + 
    "\r\n \"submitted_time\": \"2018-11-02T15:00:00Z\"," +
    "\r\n \"platform\": \"android\"," +
    "\r\n \"subject_identities\": [\r\n" +
    "{ \r\n \"identity_type\": \"android_advertising_id\"," +
    "\r\n \"identity_value\": \"\"," + 
    "\r\n \"identity_format\": \"raw\"\r\n }" + 
    "\r\n ]," + 
    "\r\n \"property_id\": \"com.example.application\"}";

    request.AddParameter("undefined", body,ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
    // handle response by reading response.StatusCode
    Console.WriteLine(response.Content);
   }
  }
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. État de la demande">

Chaque demande RGPD peut être interrogée ultérieurement pour connaître son état, en spécifiant le `subject_request_id`. Il existe 4 types d'état pris en charge :

1. ***pending*** - Une demande correcte a été reçue et est actuellement en file d'attente
2. ***in\_progress*** - Une demande est actuellement en cours d'exécution
3. ***completed*** - Une demande a été satisfaite
4. ***cancelled*** - Une demande a été annulée

<div id="status-request-format" />

### Format de l'état de la demande

Une demande d'état peut être envoyée via HTTP GET au point de terminaison suivant :

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

### Exemple de réponse concernant l'état

```http
HTTP/1.1 200 OK
Content-Type: application/json
X-OpenGDPR-Processor Domain: example processor.com
X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

<div id="status-postbacks" />

### Postbacks de l'état

Tel que décrit dans la section Flux de demande RGPD ci-dessus, lorsque l'état de la demande RGPD passe de ***pending*** à ***in\_progress*** à ***completed***, AppsFlyer envoi un postback RGPD aux points de terminaisons demandeurs, spécifiée avec la propriété **status\_callback\_urls** .

Exemple de postback d'état :

```http
POST /opengdpr_callbacks HTTP/1.1
Host: examplecontroller.com
Content-Type: application/json
X-OpenGDPR-Processor Domain: gdpr.appsflyer.com
X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

<div id="validate-postback" />

### Valider le postback

**Pour valider l'authenticité des postbacks entrants**:

1. Créez une liste de tous les domaines de processeurs que vous autorisez à effectuer des rappels.
2. Si la valeur de l'en-tête `X-OpenGDPR-Processor-Domain` figure dans votre liste d'autorisations, récupérez le certificat.
   * L'URL du certificat est la valeur de `processor_certificate` dans le corps de la réponse `/discovery`.
   * Vous pouvez également récupérer le certificat directement à partir du point de terminaison AppsFlyer en utilisant le jeton API V2 comme jeton porteur dans l'en-tête d'autorisation : `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Valider le certificat à l'aide d'une bibliothèque pour confirmer qu'il est :
   1. Délivré par une autorité de confiance.
   2. Délivré à la même chaîne que celle fournie dans la valeur de l'en-tête `X-OpenGDPR-Processor-Domain`.
   3. Toujours valide.
4. Une fois que vous avez confirmé la validité du certificat, utilisez-le pour valider l'en-tête `X-OpenGDPR-Signature` par rapport au corps de la demande brute. AppsFlyer utilise SHA256 RSA comme algorithme de signature.
5. Obtenir une réponse dans l'en-tête de statut :
   1. `202 Accepté` si la validation est réussie.
   2. `401 Non autorisé` si la signature n'est pas validée, ou si le domaine du processeur ne figure pas dans votre liste d'autorisations.

</Accordion>

<Accordion title="3. Demande de rapport">

Une fois qu'une **demande d'accès** ou une **demande de portabilité** a été effectuée, vous pouvez télécharger le rapport via HTTP GET au point de terminaison suivant :

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

Le rapport généré est disponible pendant quatorze jours à compter de la date d'achèvement.

</Accordion>

<Accordion title="4. Processus de demande de découverte">

Pour en savoir plus sur les formats pris en charge par AppsFlyer, une demande de découverte peut être soumise via HTTP GET au point de terminaison suivant :

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

### Exemple de réponse à une demande de découverte

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
 "api_version": "0.1",
 "supported_identities": [
 {
  "identity_type": "android_advertising_id",
  "identity_format": "raw"
 },
 ],
 "supported_subject_request_types": [
 "erasure", "access", "portability", "rectification"
 ],
 "processor_certificate": "https://exampleprocessor.com/cert.pem"
}
```

</Accordion>

<Accordion title="5. Demande d'annulation">

Il est possible d'annuler une demande RGPD selon son `subject_request_id`, mais uniquement pendant la phase ***pending***.

Pour envoyer un HTTP DELETE avec `subject_request_id` :

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

### Réponse à une demande d'annulation

Lors de la réception d'une demande d'annulation RGPD, AppsFlyer renvoie une réponse HTTP avec le code d'état 202 et plusieurs autres paramètres.

Une fois l'annulation de la demande effectuée, AppsFlyer envoie un postback avec l'état ***annulé***.

</Accordion>

<Accordion title="6. API de test des demandes RGPD">

Cette API AppsFlyer est une API test pour l'API des demandes RGPD d'AppsFlyer.

<div id="how-does-it-work" />

### Comment fonctionne l'API de test ?

L'API de test fonctionne comme suit :

1. Une fois qu'une demande RGPD a été effectuée, celle-ci passe immédiatement à l'état « Pending ». À des fins de test, l'état change toutes les 30 secondes.

2. Si un point de terminaison pour un postback d'état a été inséré dans la demande RGPD, un premier postback est envoyé directement après la demande, et deux autres postbacks d'état sont envoyées par intervalles de 30 secondes.

**Point de terminaison du test de demande RGPD** : POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Point de terminaison du test de demande d'état** : GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Point de terminaison du test de demande de découverte** : GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Point de terminaison du test de demande d'annulation** : DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Point final du test de certificat** : GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Point final du test d'accès/de portabilité** : GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

<div id="note" />

> 📘 **Remarques**
>
> * Un jeton API V2 valide doit être présent dans l'en-tête de la demande comme suit : `'Authorization' : 'Bearer %AuthTokenV2%'`
> * Dans la propriété « property\_id », l'ID de l'app doit appartenir au propriétaire du compte (en fonction du token de l'API).

</Accordion>

<Accordion title="7. Demande de journaux">

L'admin de compte peut accéder aux demandes de RGPD soumises dans le tableau de bord des journaux.

Pour les demandes d'accès et de portabilité terminées, il est également possible de télécharger le rapport depuis ce tableau de bord.

Pour accéder au tableau de bord Logs :

1. Rendez-vous sur le tableau de bord principal et cliquez sur votre nom d'utilisateur.
2. Cliquez sur **Logs** pour ouvrir la fenêtre suivante :

<Image align="center" alt="GDPR_Table.png" src="https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png" />

</Accordion>

<Accordion title="8. Codes de retour et messages d'erreur de l'API de demande RGPD">

Les codes de retour et messages d'erreur HTTP de l'API de demande RGPD sont présentés dans ce chapitre.

<div id="gdpr-api-return-codes" />

#### Codes de retour d'API de demande RGPD

| Code de retour | Description |
| --- | --- |
| 201 | Créé |
| 202 | Demande d'annulation reçue |
| 400 | Demande incorrecte. Le corps contient le code et le message d'erreur tels qu'indiqués dans le tableau suivant. |

<div id="http-return-code-400---bad-request" />

### Code de retour HTTP 400 - demande incorrecte

Les messages avec code de retour 400 contiennent un JSON indiquant le code et le message d'erreur.

`{ "error":{ "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%"}}`

<div id="return-code-400-bad-request-messages" />

#### Code de retour 400, messages de demande incorrecte

| Code d'erreur | Description de l'erreur (message) |
| --- | --- |
| e111 | Taux maximal dépassé |
| e211 | Impossible d'annuler une demande dont le statut est invalide |
| e212 | Demande non autorisée. L'effacement d'identifiant est en cours. |
| e213 | La demande existe déjà |
| e214 | Demande non trouvée |
| e311 | Type de contenu de demande invalide |
| e312 | Version d'API invalide |
| e313 | subject\_request\_id invalide |
| e314 | Format de submit\_time invalide |
| e315 | Longueur de status\_callback\_url invalide |
| e316 | Format de status\_callback\_url invalide |
| e317 | Format de app\_id invalide |
| e318 | identity\_type invalide |
| e319 | La plate-forme d'application ne correspond pas aux types d'identité |
| e320 | identity\_type invalide |
| e321 | Utilisateurs LAT non pris en charge via api |
| e322 | subject\_request\_type invalide |
| e323 | Format de subject\_identities invalide |
| e324 | Longueur de subject\_identities invalide |
| e325 | Valeur de subject\_identities invalide |
| e411 | L'ID d'app est incorrect ou ne fait pas partie de votre compte |
| e412 | Vous n'avez pas l'autorisation pour annuler la demande d'effacement |
| e413 | Vous n'avez pas l'autorisation pour afficher la demande |
| e511 | Problème interne, veuillez patienter 60 minutes avant de réessayer. Si le problème persiste, contactez l'assistance AppsFlyer. support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## Particularités et limites

* Limitation du taux : 80 demandes RGPD toutes les 2 minutes au niveau du compte (ce qui équivaut à 2 400 demandes par heure et 57 600 par jour). **Les demandes dépassant cette limite seront rejetées.**
* L'interface utilisateur affiche jusqu'à 200 demandes sélectionnées de manière aléatoire.
* La vérification de l'état d'une demande datant de plus de 60 jours renvoie le message suivant : demande non trouvée.