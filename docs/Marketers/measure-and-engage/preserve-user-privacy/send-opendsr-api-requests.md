---
title: "Send OpenDSR API requests"
excerpt: "Implement the OpenDSR API to comply with global data protection laws and manage user data requests."
x-zendesk:
  id: 11332840660625
  url: https://support.appsflyer.com/hc/en-us/articles/11332840660625-Send-OpenDSR-API-requests
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Preserve user privacy
  section_id: 6551440878097
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, GDPR, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2026-10-01T15:42:01Z'
---
This article is for the use of AppsFlyer clients, often referred to as Advertisers or App Owners, using the Platform to record app use and attribution. App Owners implement OpenDSR (Data Subject Request) API to comply with applicable data protection laws like GDPR (Europe), CCPA (California), LGPD (Brazil), PDPA (Thailand), and PIPA (Korea).

**A word from our lawyers:** *Nothing stated here is legal advice. It is provided for your information and convenience. You should work closely with legal and other professional advisors to determine exactly how GDPR, CCPA, or any other laws may or may not apply to you.* The privacy relationship between you and AppsFlyer is governed by the [AppsFlyer Services Privacy Policy](https://www.appsflyer.com/services-privacy-policy). For any questions relating to this Services Privacy Policy or to contact our data protection officer please send us a mail to [privacy@appsflyer.com](mailto:privacy@appsflyer.com). For the purposes of Article 27 of the General Data Protection Regulation, the representative within the EU of AppsFlyer is AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Germany (contact [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).

## Privacy regulations

In this article, references to privacy regulations include the regulations listed in the table that follows.

| Regulation | Logo | Description |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | The General Data Protection Regulation is the EU regulation relating to data protection and privacy for European Union citizens |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | California Consumer Privacy Act |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Personal Data Protection Act |

The terms privacy regulations, GDPR, CCPA, LGPD, and PDPA are used interchangeably in this article.

### The OpenDSR initiative

To address and manage requests by Data Subjects submitted in accordance with privacy regulations, AppsFlyer, together with mParticle, Amplitude, and Braze, initiated the OpenDSR protocol (formerly known as OpenGDPR).

OpenDSR is an open-source framework, that facilitates cooperation between technology companies for the fair and transparent use of consumer data. It enables vendors to take data privacy actions across multiple systems that process and store customer data.

[Learn more about the OpenDSR initiative](https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/).

### Definitions

| DSR Term | AppsFlyer Term | Description |
| --- | --- | --- |
| Data Subject | App User or End-user | The App User about whom data is collected |
| Data Controller | App Owner or Advertiser | The App Owner determines the purpose and means by which the personal data is processed. |
| Data Processor | AppsFlyer and its partners | AppsFlyer and its partners process personal data on behalf of the data controller |

### DSR requirements

DSR details the mandatory rights of the Data Subject, with which the Data Controller must comply. For API purposes these rights are translated into request types. The following details how AppsFlyer processes the different request types.

| **Request type**<br /><br />**(Right)** | **GDPR definition** | Processing of the request by AppsFlyer |
| --- | --- | --- |
| **Access** | * If requested, App Users have the right to know if, why, and for how long the App Owner will process their data.<br />* If data is shared with third parties, like AppsFlyer, App Users have the right to know who those third parties are.<br />* The right to know what categories of data are being processed.<br />* If there is automated processing, that has a significant effect on them. | The App Owners receive a copy of the App Users' processed personal data. |
| **Portability** | The App User needs to receive all of their personal data in a structured, commonly used, and machine-readable format, such as a CSV file. | The App Owner receives a copy of the App User's processed personal data. |
| **Rectification** | Allows App Users to correct their data if they see it is inaccurate or untruthful. App Owners are required to erase or correct inaccurate or incomplete data. | * AppsFlyer deletes the App User's data recorded prior to the date of the *rectification* request.<br />* Data received thereafter is recorded by AppsFlyer. |
| **Erasure** | The right of erasure requires App Owners to remove personal data within 10 days of receiving the request. | The data is deleted |

## AppsFlyer GDPR Requests API

Use the GDPR Requests API as described in this section to implement DSR compliance.

* **GDPR Request:** Perform one of the above request types: access, portability, erasure, rectification.
* **Status Request**: Query the current status of a GDPR request.
* **Discovery Request**:Inquire as to the supported API version and Data Format.
* **Cancellation**:Cancel a GDPR request during its ***pending*** phase.

App Owners must implement UI changes to their app so that App Users can submit requests. Note that GDPR requests are per single user at one time.

<Accordion title="1. GDPR request">

#### GDPR request flow

The GDPR request types, Access, Portability, Erasure, and Rectification, have the following flow:

1. **App User** submits a request.
2. **The App Owner** constructs the GDPR request (see below) and sends it to AppsFlyer.
3. **AppsFlyer** receives the request and responds with a "201 OK" for valid requests.
4. **For Access and Portability:** Requests are fulfilled within 8 days.  
   **Note:** This 8-day period begins when the App Owner submits their request. The request status changes to In Progress from pending and will be completed within an additional 6 days, totaling 8 days.  
   **For Erasure and Rectification:**
   * During the following 48 hours, the request is queued and has a ***pending*** status. The App User may cancel the request.
   * After 48 hours, the request status changes to ***in\_progress.*** AppsFlyer sends a ***status change*** postback. At this point, the request can't be canceled.
   * Within 10 days (see note below), AppsFlyer fulfills the request, and the request status changes to ***completed***. AppsFlyer sends a status change postback.

     * In the case of *erasure* or *rectification*, the App User's data is deleted.
     * In the case of *portability* or *access,* the App User's data can be accessed in the AppsFlyer dashboard under **GDPR** or via the Request API (see below).

     **Note:** This 10-day period begins when the App Owner submits their request. After 48 hours, the request status changes to **In Progress** and will be completed within an additional 8 days, totaling 10 days.

#### GDPR request format

A GDPR Request API can be submitted via HTTP POST to the following endpoint:

```
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

For the API authorization, use the same V2 API token as for Pull API. An admin user can [retrieve the token](/docs/managing-appsflyer-tokens#retrieving-api-tokens) from the API token page in the dashboard. Add the token into the request header as follows: `'Authorization': 'Bearer %AuthTokenV2%'`

#### Parameters

<table><thead><tr><th><strong>Property Name</strong></th><th><strong>Mandatory</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Yes</td><td>UUID v4 string. Generated by the controller at the time of request submission to a Processor. It can then be used in order to check the status of the request, update or cancel it.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Yes</td><td><p>String value representing the type of GDPR Request. Supported values:</p><ul><li>erasure</li><li>portability</li><li>access</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Yes</td><td><ul><li>An array of identity objects defining the requester's identity (see below).</li><li>Each request can contain only one subject identity.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Yes</td><td><ul><li>RFC 3339 date string of the time of the original request by the data subject</li><li>Timestamps in UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Yes</td><td><p>String representing the mobile app to which this request is scoped:</p><p><strong>Examples</strong>:</p><ul><li><strong>iOS</strong>: id123456789</li><li><strong>Android</strong>: com.example, com.publishers.name</li><li><strong>Android out-of-store</strong>: com.publisher.name-channel<br/><strong>Note </strong>In some cases, App Owners record out-of-store attribution using the Android Google Play name. In these cases use the regular app name as it displays in the Dashboard.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>No</td><td>Version string representing the desired version of the GDPR Requests API</td></tr><tr><td><strong>status_callback_urls</strong></td><td>No, but recommended</td><td><ul><li>An array of up to 3 endpoints for status callbacks to be sent to the following request status changes.</li><li>Only HTTPS endpoints are supported.</li><li>Invalid URLs are rejected.</li></ul></td></tr><tr><td rowspan="2"><strong>platform</strong><br/><br/> </td><td>No</td><td>Value is one of the supported DSR platforms:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code></td></tr><tr><td>Yes</td><td><p>For a CTV, PC, or Console platform request, include any of the following platforms:</p><p><code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

#### Subject\_identities objects

| Object type | **Mandatory** | **Description** |
| --- | --- | --- |
| identity\_type | Yes | * The identity type in string format for `android`, `ios`, `web`, `windowsphone` platforms are any of the following:<br />  * ios\_advertising\_id<br />  * android\_advertising\_id<br />  * fire\_advertising\_id<br />  * microsoft\_advertising\_id<br />  * appsflyer\_id<br />  * customer\_user\_id (CUID)<br /><br />* For `CTV`, `PC`, and `Console`platforms only the following:<br />  * appsflyer\_id<br />  * customer\_user\_id (CUID)<br /><br />* Example: `android_advertising_id`<br /><br />**Important!**<br /><br />To use CUID through the OpenDSR API, you must send the CUID with `idfa` / `appsflyer_id` inside in-app events using `event_name`: `Login - Complete` or `Registration - Account created` |
| identity\_value | Yes | * Format: String<br />* Example: "a7551968-d5d6-44b2-9831-815ac9017798" |
| identity\_format | Yes | * The method used to encode the identity\_value: `raw` is the only supported:<br />* Example: "raw" |

#### Example: GDPR erasure request

**Example of an erasure request for** `android`**,** `ios`**,** `web`**,** `windowsphone` **platforms:**

```
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
 "status_callback_urls":[
  "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

**Example of an erasure request for**`CTV`**,** `PC`**, and** `Console` **platforms:**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
"subject_request_type":"erasure",
"submitted_time":"2020-07-05T10:00:00Z",
"subject_identities":[
 {
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
"api_version":"0.1",
"property_id":"app-id",
"platform": "roku",
"status_callback_urls":[
 "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

#### GDPR erasure request code example

<Accordion title="Java">

```
/*
using the okhttp package install from maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */

import okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null, "" +
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

</Accordion>

<Accordion title="PythonNode.jsC#">

```
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
"https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests",
headers=headers, data=body, params=params)
print(res.text)
```

```
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

```
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

</Accordion>

</Accordion>

<Accordion title="2. Status request">

Every submitted GDPR request can be later queried for its status, by specifying the `subject_request_id`. There are four supported status types:

1. ***pending*** - A correct request has been received and is currently in the queue
2. ***in\_progress*** - A request is currently being acted on
3. ***completed*** - A request has been fulfilled
4. ***canceled*** - A request has been canceled

#### Status request format

A status request can be submitted via HTTP GET to the following endpoint:

```
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

#### Status response example

```
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

#### Status postbacks

As described in the GDPR Request Flow above, when the status of a GDPR request changes, from ***pending*** to ***in\_progress*** to ***completed***, AppsFlyer sends a GDPR postback to the requesting endpoints, specified with the **status\_callback\_urls** property.

Status postback example:

```
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

#### Validate postback

**To validate the authenticity of incoming postbacks**:

1. Create an allowlist of all the processor domains that you allow to make callbacks.
2. If the header value for `X-OpenGDPR-Processor-Domain` is in your allowlist, fetch the certificate.
   * The certificate URL is the value of `processor_certificate` in the `/discovery` response body.
   * You can also fetch the certificate directly from the AppsFlyer endpoint using the V2 API token as a bearer token in the authorization header: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Validate the certificate using a library to confirm that the certificate:
   1. Is issued by a trusted authority.
   2. Is issued to the same string provided in the `X-OpenGDPR-Processor-Domain` header value.
   3. Isn’t expired.
4. Once you confirm the certificate is valid, use it to validate the `X-OpenGDPR-Signature` header against the raw request body. AppsFlyer uses SHA256 RSA as a signing algorithm.
5. Get a response in the status header:
   1. `202 Accepted` if validation is successful.
   2. `401 Unauthorized` if the signature fails to validate or the processor domain isn’t in your allowlist.

</Accordion>

<Accordion title="3. Report request">

Once an **Access Request** or **Portability Request** has been completed, you can download the report via HTTP GET to the following endpoint:

```
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

The generated report is available for fourteen days from the time of completion.

</Accordion>

<Accordion title="4. Discovery request-in process">

To learn about the formats supported by AppsFlyer, a discovery request can be submitted via HTTP GET to the following endpoint:

```
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

#### Discovery response example

```
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

<Accordion title="5. Cancellation request">

It is possible to cancel a GDPR request, based on its `subject_request_id`, but only during the ***pending*** phase.

To submit an HTTP DELETE with `subject_request_id` :

```
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

#### Cancellation response

When a GDPR cancellation request is received, AppsFlyer returns an HTTP response with status code 202 and several other parameters.

Once the cancellation of the request takes place AppsFlyer sends a postback with the ***canceled*** status.

</Accordion>

<Accordion title="6. GDPR requests test API">

This AppsFlyer API is a test API for the AppsFlyer's GDPR Requests API.

#### How does it work?

The test API works as follows:

1. Once a GDPR request has been made, the request is immediately placed in ‘Pending’ status. For testing purposes, the status changes every 30 seconds.

2. If an endpoint for a status postback has been inserted in the GDPR request, a first postback is sent right after the request and two more status postbacks are sent in 30-second intervals.

**GDPR Request Test Endpoint**: POST

```
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Status Request Test Endpoint**: GET

```
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Discovery Request Test Endpoint**: GET

```
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Cancellation Request Test Endpoint**: DELETE

```
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Certificate Test Endpoint**: GET

```
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Access/Portability Reports Test Endpoint**: GET

```
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

**Notes**

* A valid V2 API token must be inserted into the request header as follows: `'Authorization': 'Bearer %AuthTokenV2%'`
* In the ‘property\_id’ property, the App ID must belong to the account owner (according to the API token).

</Accordion>

<Accordion title="7. Request logs">

An admin user can access the GDPR requests submitted in the Logs Dashboard.

For completed access and portability requests, it is also possible to download the report from within this dashboard.

To access the Logs Dashboard:

1. From the top bar, open the account menu (email address dropdown) > **E-GDPR log**.
2. The following window opens:

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<Accordion title="8. GDPR API return codes and error messages">

The GDPR API HTTP return codes and error messages are detailed in this section.

#### GDPR API return codes

| Return code | Description |
| --- | --- |
| 201 | Created |
| 202 | Cancelation request received |
| 400 | Bad request. The body contains the error code and message as listed in the table that follows. |

#### HTTP return code 400 - bad request

Messages having return code 400 contain a JSON with the error code and message.

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

#### Return code 400 bad request messages

| Error code | Error description (message) |
| --- | --- |
| e211 | Unable to cancel request with invalid status |
| e212 | Request not permitted. Erasure is in progress for the identifier. |
| e213 | Request already exists |
| e214 | Request not found |
| e215 | One or more subject-identities already exist in an open request. if another request for the same identity\_value is currently open in ‘pending’ or ‘in\_progress’ state. |
| e311 | Invalid request content-type |
| e312 | Invalid API version |
| e313 | Invalid subject\_request\_id |
| e314 | Invalid submitted\_time format |
| e315 | Invalid status\_callback\_url length |
| e316 | Invalid status\_callback\_url format |
| e317 | Invalid app\_id format |
| e318 | Invalid identity\_type |
| e319 | Application platform does not match identity types |
| e321 | LAT users are not supported via api |
| e322 | Invalid subject\_request\_type |
| e323 | Invalid subject\_identities format |
| e324 | Invalid subject\_identities length |
| e325 | Invalid subject\_identities value |
| e326 | Invalid JSON format in request body |
| e411 | AppID is incorrect or does not belong to your account |
| e412 | No permissions to cancel erasure request |
| e413 | No permissions to view request |
| e511 | Internal problem, wait 60 minutes and try again. If the problem persists contact AppsFlyer support. support@AppsFlyer.com |

</Accordion>

## Traits and limitations

* **OpenDSR API rate limit: 350 requests per minute**. Exceeding this limit will result in an error, requiring the request to be resent. Staying within this rate limit allows for up to 504,000 requests per day.
* Checking the status of a request from more than 60 days ago returns "request not found".