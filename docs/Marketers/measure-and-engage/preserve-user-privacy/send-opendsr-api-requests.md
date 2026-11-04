---
title: Enviar solicitudes a la API de OpenDSR
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
  edited_at: '2026-10-03T00:16:55Z'
  id: 11332840660625
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/11332840660625
---
> **At a glance:** Este artículo es para los clientes de AppsFlyer, a menudo denominados anunciantes o propietarios de aplicaciones, que usan la plataforma para registrar la atribución y el uso de aplicaciones. Los propietarios de aplicaciones implementan la API OpenDSR (Data Subject Request) para cumplir con las leyes de protección de datos aplicables como el GDPR (Europa), CCPA (California), LGPD (Brasil), PDPA (Tailandia) y PIPA (Corea).

**Una nota de nuestros abogados:** *Nada de lo indicado aquí constituye asesoramiento jurídico. Se proporciona para tu información y comodidad. Deberías trabajar en estrecha colaboración con asesores legales y otros profesionales para determinar exactamente cómo el GDPR, CCPA o cualquier otra ley puede o no aplicarse a ti. La relación de privacidad entre tú y AppsFlyer se rige por la <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">Política de privacidad de servicios de AppsFlyer</Anchor>. Para preguntas relacionadas con esta Política de Privacidad de Servicios o para contactar con nuestro responsable de protección de datos, envía un correo a [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Para efectos del Artículo 27 del Reglamento General de Protección de Datos, el representante dentro de la UE de AppsFlyer es **AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlín, Alemania (contacto [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).***

<div id="privacy-regulations" />

## Regulaciones de privacidad

En este artículo, las referencias a las normas de privacidad incluyen las normas enumeradas en la tabla que figura a continuación.

| Norma | Logotipo | Descripción |
| --- | --- | --- |
| RGPD | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | El Reglamento General de Protección de Datos es el conjunto de normas de la UE en materia de protección de datos y privacidad de los ciudadanos de la Unión Europea. |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | Ley de Privacidad del Consumidor de California |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Ley de Protección de Datos Personales |

Los términos "normativas de privacidad", "GDPR", "CCPA", "LGPD" y "PDPA" se usan indistintamente en este artículo.

<div id="the-opendsr-initiative" />

### La iniciativa OpenDSR

Para atender y administrar las solicitudes de los sujetos de datos de acuerdo con las regulaciones de privacidad, AppsFlyer, junto con mParticle, Amplitude y Braze, iniciaron el protocolo OpenDSR (anteriormente conocido como OpenGDPR).

OpenDSR es un framework de código abierto y unificado que facilita la cooperación entre empresas de tecnología para el uso justo y transparente de los datos de consumidores. Permite a los proveedores tomar acciones de privacidad de datos en múltiples sistemas que procesan y almacenan datos de clientes.

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">Saber más sobre la iniciativa OpenDSR</Anchor>.

<div id="definitions" />

### Definiciones

| Término DSR | Término de AppsFlyer | Descripción |
| --- | --- | --- |
| Sujeto de datos | Usuario de la aplicación o usuario final | El usuario de la aplicación sobre el que se recopilan los datos |
| Controlador de datos | Propietario de la aplicación o anunciante | El propietario de la aplicación determina el propósito y los medios por los cuales se procesan los datos personales. |
| Procesador de datos | AppsFlyer y sus partners | AppsFlyer y sus partners procesan datos personales en nombre del controlador de datos. |

<div id="dsr-requirements" />

### Requisitos de DSR

En el DSR se detallan los derechos obligatorios del sujeto de datos, que el controlador de datos debe cumplir. Para fines de API, estos derechos se traducen en tipos de solicitud. A continuación se detalla cómo AppsFlyer procesa los diferentes tipos de solicitud.

| **Tipo de solicitud**<br /><br />**(Derecho)** | **Definición según el GDPR** | Procesamiento de la solicitud por parte de AppsFlyer |
| --- | --- | --- |
| **Acceso** | <ul><li>Si lo solicitan, los usuarios de la aplicación tienen derecho a saber si, por qué y durante cuánto tiempo el propietario de la aplicación procesará sus datos.</li><li>Si los datos se comparten con terceros, como AppsFlyer, los usuarios de la aplicación tienen derecho a saber quiénes son esos terceros.</li><li>También tienen derecho a saber qué categorías de datos se procesan.</li><li>Si hay procesamiento automatizado que pudiera afectarlos significativamente.</li></ul> | Los propietarios de la aplicación reciben una copia de los datos personales procesados de los usuarios de la aplicación. |
| **Portabilidad** | El usuario de la aplicación debe recibir todos sus datos personales en un formato estructurado, comúnmente utilizado y legible por máquina, como un archivo CSV. | El propietario de la aplicación recibe una copia de los datos personales procesados del usuario de la aplicación. |
| **Rectificación** | Permite a los usuarios de la aplicación corregir sus datos si ven que son inexactos o falsos. Los propietarios de aplicaciones están obligados a eliminar o corregir los datos inexactos o incompletos. | <ul><li>AppsFlyer elimina los datos del usuario de la aplicación registrados antes de la fecha de la *solicitud de rectificación*.</li><li>Los datos recibidos a partir de entonces son registrados por AppsFlyer.</li></ul> |
| **Eliminación** | El derecho de eliminación obliga a los propietarios de aplicaciones a eliminar los datos personales dentro de un plazo de 10 días después de la recepción de la solicitud. | Los datos se eliminan |

<div id="appsflyer-gdpr-requests-api" />

## API de solicitudes GDPR de AppsFlyer

Usa la API de solicitudes de GDPR tal como se describe en esta sección para implementar el cumplimiento normativo del DSR.

* **Solicitud de RGPD:** Realiza uno de los tipos de solicitud anteriores: acceso, portabilidad, supresión, rectificación.
* **Solicitud de estado**: Consulta el estado actual de una solicitud GDPR.
* **Solicitud de descubrimiento**: Consulta la versión de la API compatible y el formato de datos.
* **Cancelación**: Cancela una solicitud de RGPD durante su fase ***pendiente***.

Los propietarios de aplicaciones deben implementar cambios en la interfaz de usuario de su aplicación, de modo que los usuarios de la aplicación puedan enviar solicitudes. Debes tener en cuenta que las solicitudes GDPR se envían de a un usuario por vez.

<Accordion title="1. Solicitud de RGPD">

<div id="gdpr-request-flow" />

#### Flujo de solicitudes GDPR

Los tipos de solicitud GDPR, Acceso, Portabilidad, Eliminación y Rectificación, tienen el mismo flujo:

1. **Usuario de la aplicación** envía una solicitud.
2. **El propietario de la aplicación** genera la solicitud de GDPR (ver más abajo) y la envía a AppsFlyer.
3. **AppsFlyer** recibe la solicitud y responde con un "201 OK" para las solicitudes válidas.
4. **Para acceso y portabilidad:** Las solicitudes se completan en un plazo de 8 días.  
   **Nota:** Este período de 8 días comienza cuando el propietario de la aplicación envía su solicitud. El estado de la solicitud cambia a “En Progreso” de pendiente y se completará dentro de 6 días adicionales, totalizando 8 días.  
   **Para la eliminación y rectificación:**
   * Durante las siguientes 48 horas, la solicitud se pone en cola y queda en estado ***pendiente***. El usuario de la aplicación puede cancelar la solicitud.
   * Después de 48 horas, el estado de la solicitud cambia a ***in\_progress.*** AppsFlyer envía un postback de ***cambio de estado***. En este punto,no se puede cancelar la solicitud.
   * En un plazo de 10 días (ver la nota más abajo), AppsFlyer tramita la solicitud y el estado de la solicitud cambia a ***completed***. AppsFlyer envía un postback de cambio de estado.

     * En el caso de *eliminación* o *rectificación*, se eliminan los datos del usuario de la aplicación.
     * En el caso de *portabilidad* o *acceso,* se puede acceder a los datos del usuario de la aplicación en el dashboard de AppsFlyer, en **GDPR** o a través de la API de solicitudes (ver más abajo).

     **Nota:** Este período de 10 días comienza cuando el propietario de la aplicación envía su solicitud. Después de 48 horas, el estado de la solicitud cambia a **En progreso** y se completará en 8 días adicionales, hasta un total de 10 días.

<div id="gdpr-request-format" />

#### Formato de solicitudes GDPR

Se puede presentar una API de solicitudes GDPR por medio de HTTP POST al punto de conexión:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Para la autorización de la API, usa el mismo token de API V2 que para Pull API. Un usuario administrador puede <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#recuperar-tokens">recuperar el token</Anchor> desde la página del token de la API en el dashboard. Agrega el token en el encabezado de la solicitud de la siguiente manera: `'Authorization': 'Bearer %AuthTokenV2%'`

<div id="parameters" />

#### Parámetros

<table><thead><tr><th><strong>Nombre de propiedad</strong></th><th><strong>Obligatorio</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Sí</td><td>Secuencia UUID v4. Generada por el controlador al momento del envío de la solicitud al procesador. Luego puede utilizarse para controlar el estado de la solicitud, actualizarla o cancelarla.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Sí</td><td><p>Valor de la secuencia que representa el tipo de solicitud GDPR. Valores admitidos:</p><ul><li>erasure</li><li>portability</li><li>access</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Sí</td><td><ul><li>Una matriz de objetos de identidad que definen la identidad del solicitante (ver más abajo).</li><li>Cada solicitud puede contener solo una identidad de sujeto.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Sí</td><td><ul><li>Secuencia de fecha RFC 3339 del momento de la solicitud original enviada por el sujeto de datos</li><li>Marcas de tiempo en UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Sí</td><td><p>Cadena que representa la aplicación móvil con la cual está relacionada esta solicitud.</p><p><strong>Ejemplos</strong>:</p><ul><li> <strong>iOS</strong>: id123456789</li><li> <strong>Android</strong>: com.example, com.publishers.name</li><li> <strong>Android fuera de la tienda</strong>: com.publisher.name-channel<br/><strong>Nota</strong> En algunos casos, los propietarios de aplicaciones registran la atribución fuera de la tienda con el nombre de Google Play de Android. En estos casos, usa el nombre normal de la aplicación tal como se muestra en el panel de control.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>No</td><td>Cadena de versión que representa la versión deseada de la API de Solicitudes GDPR.</td></tr><tr><td><strong>status_callback_urls</strong></td><td>No, pero recomendado</td><td><ul><li>Matriz de hasta 3 puntos de conexión para que las devoluciones de llamadas de estado se envíen a los siguientes cambios de estado de solicitud.</li><li>Solo se admiten puntos de conexión HTTPS.</li><li>Se rechazan las URL no válidas.</li></ul></td></tr><tr><td rowspan="2"> <strong>plataforma</strong><br/><br/> </td><td>No</td><td>El valor es una de las plataformas DSR admitidas:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code> </td></tr><tr><td>Sí</td><td><p>Para una solicitud de plataforma de CTV, PC o Consola, incluye cualquiera de las siguientes plataformas: </p><p><code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Objetos subject\_identities

| Tipo de objeto | **Obligatorio** | **Description** |
| --- | --- | --- |
| identity\_type | Sí | <ul><li>Los tipos de identidad en formato string para las plataformas `android`, `ios`, `web` y `windowsphone` son los siguientes:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Solo para las plataformas `CTV`, `PC` y `Console`: únicamente los siguientes:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Ejemplo: `android_advertising_id`</li></ul>**Important**<br />**Importante:**<br /><br />Para usar CUID a través de la API de OpenDSR, debes enviar el CUID con `idfa` / `appsflyer_id` dentro de los eventos in-app mediante `event_name`: `Login - Complete` o `Registration - Account created` |
| identity\_value | Sí | <ul><li>Formato: Secuencia</li><li>Ejemplo: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | Sí | <ul><li>El método utilizado para codificar el identity\_value: `raw` es el único compatible:</li><li>Ejemplo: "raw"</li></ul> |

<div id="example-gdpr-erasure-request" />

#### Ejemplo: Solicitud de eliminación de GDPR

**Ejemplo de una solicitud de eliminación para las plataformas** `android`, `ios`, `web` **y** `windowsphone`:

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
 "status_callback_urls":[
  "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

**Ejemplo de una solicitud de eliminación para las plataformas** `CTV`, `PC` **y** `Console`:

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2%' \
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

<div id="zd-gdpr-erasure-request-code-example" />

<div id="gdpr-erasure-request-code-example" />

#### Ejemplo de código de solicitud de borrado GDPR

<Tabs>
<Tab title="Java">

```java
/*
usando el paquete okhttp instalado desde maven
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

</Tab>

<Tab title="Python Node.js C#">

```python
""" usando el paquete requests de Python,
instálalo con pip install requests """

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

```javascript
/* usando el paquete request de npm,
instálalo con npm install request */

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
    // gestiona la respuesta leyendo response.StatusCode
    Console.WriteLine(response.Content);
   }
  }
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Solicitud del estado">

Cada solicitud de GDPR enviada puede consultarse más adelante para conocer su estado, especificando el `subject_request_id`. Existen cuatro tipos de estado admitidos:

1. ***pending*** - Se ha recibido una solicitud correcta y actualmente está en la cola
2. ***in\_progress*** - Actualmente se está procesando una solicitud
3. ***completed*** - Se ha completado una solicitud
4. ***canceled*** - Se ha cancelado una solicitud

<div id="status-request-format" />

#### Formato de solicitud de estado

Se puede presentar una solicitud de estado por medio de HTTP GET al punto de conexión

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

#### Ejemplo de respuesta de estado

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

#### Postbacks de estado

Como se describe arriba en el GDPR Request Flow, cuando cambia el estado de una solicitud de GDPR, de ***pending*** a ***in\_progress*** y luego a ***completed***, AppsFlyer envía un postback de GDPR a los endpoints solicitantes especificados con la propiedad **status\_callback\_urls**.

Ejemplo de postback de estado:

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

#### Validar postback

**Para validar la autenticidad de los postbacks entrantes**:

1. Crea una lista de permitidos de todos los dominios de procesador a los que permitas realizar devoluciones de llamada.
2. Si el valor del encabezado `X-OpenGDPR-Processor-Domain` está en tu allowlist, obtén el certificado.
   * La URL del certificado es el valor de `processor_certificate` en el cuerpo de la respuesta de `/discovery`.
   * También puedes obtener el certificado directamente desde el endpoint de AppsFlyer usando el token de API V2 como bearer token en el encabezado de autorización: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Valida el certificado usando una biblioteca para confirmar que el certificado:
   1. ha sido emitido por una autoridad de confianza.
   2. Se emite para el mismo string proporcionado en el valor del encabezado `X-OpenGDPR-Processor-Domain`.
   3. no ha expirado.
4. Una vez que confirmes que el certificado es válido, utilízalo para validar el encabezado `X-OpenGDPR-Signature` contra el cuerpo sin procesar de la solicitud. AppsFlyer utiliza SHA256 RSA como algoritmo de firma.
5. Obtén una respuesta en el encabezado de estado:
   1. `202 Accepted` si la validación se realiza correctamente.
   2. `401 Unauthorized` si no se puede validar la firma o el dominio del procesador no está en tu allowlist.

</Accordion>

<Accordion title="3. Solicitud de reporte">

Una vez que se haya completado una **Solicitud de acceso** o una **Solicitud de portabilidad**, puedes descargar el reporte mediante HTTP GET en el siguiente endpoint:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

El reporte generado estará disponible durante 14 días a partir de la finalización.

</Accordion>

<Accordion title="4. Proceso de solicitud de descubrimiento">

Para conocer los formatos admitidos por AppsFlyer, se puede enviar una solicitud de descubrimiento mediante HTTP GET al siguiente punto de conexión:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

#### Ejemplo de respuesta de descubrimiento

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

<Accordion title="5. Solicitud de cancelación">

Es posible cancelar una solicitud GDPR en función de su `subject_request_id`, pero solo durante la fase ***pending***.

Para enviar una solicitud HTTP DELETE con `subject_request_id`:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

#### Respuesta de cancelación

Cuando se recibe una solicitud de cancelación GDPR, AppsFlyer devuelve una respuesta HTTP con el código de estado 202 y varios parámetros más.

Una vez que se produce la cancelación de la solicitud, AppsFlyer envía un postback con el estado ***canceled*** .

</Accordion>

<Accordion title="6. API de prueba de solicitudes GDPR">

Esta API de AppsFlyer es una API de prueba para la API de solicitudes GDPR de AppsFlyer.

<div id="how-does-it-work" />

#### ¿Cómo funciona?

La API de prueba funciona de la siguiente manera:

1. Una vez presentada una solicitud GDPR, inmediatamente se le asigna el estado "Pendiente". A los fines de la prueba, el estado cambia cada 30 segundos.

2. Si se insertó un punto de conexión para un postback de estado en la solicitud GDPR, se envía un primer postback inmediatamente después de la solicitud, y dos postbacks de estado más con intervalos de 30 segundos.

**Punto de conexión de prueba de solicitud GDPR**: POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Punto de conexión de prueba de solicitud de estado**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Punto de conexión de prueba de solicitud de descubrimiento**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Punto de conexión de prueba de solicitud de cancelación**: DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Punto de conexión de prueba del certificado**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Punto de conexión de prueba de reportes de acceso/portabilidad**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **Note**
>
> **Notas**
>
> * Se debe insertar un token de API V2 válido en el encabezado de la solicitud de la siguiente manera: `'Authorization': 'Bearer %AuthTokenV2%'`
> * En la propiedad "property\_id", el ID de la aplicación debe corresponder al propietario de la cuenta (de acuerdo con el token de la API).

</Accordion>

<Accordion title="7. Registros de solicitudes">

Un usuario administrador puede acceder a las solicitudes de RGPD enviadas en el Panel de control de registros.

En el caso de las solicitudes de acceso y portabilidad finalizadas, también es posible descargar el reporte desde este panel de control.

Para acceder al panel de control de registros:

1. En la barra superior, abre el menú de la cuenta (menú desplegable de la dirección de correo electrónico) > **E-GDPR log**.
2. Se abrirá la siguiente ventana:

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<Accordion title="8. Mensajes de error y códigos de retorno de la API de GDPR">

Los mensajes de error y códigos de retorno HTTP de la API de GDPR se detallan en esta sección.

<div id="gdpr-api-return-codes" />

#### Códigos de retorno de la API de GDPR

| Código de respuesta | Descripción |
| --- | --- |
| 201 | Creada |
| 202 | Solicitud de cancelación recibida |
| 400 | Solicitud incorrecta. El cuerpo contiene el mensaje y código de error tal como se enumeran en la tabla a continuación. |

<div id="http-return-code-400---bad-request" />

#### Código de retorno HTTP 400: solicitud incorrecta

Los mensajes que tienen el código de retorno 400 contienen un JSON con el mensaje y código de error.

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

<div id="return-code-400-bad-request-messages" />

#### Mensajes de solicitud incorrectos, código de retorno 400

| Código del error | Descripción del error (mensaje) |
| --- | --- |
| e211 | No se puede cancelar la solicitud con un estado inválido |
| e212 | Solicitud no permitida. La eliminación está en curso para el identificador. |
| e213 | La solicitud ya existe |
| e214 | No se encontró la solicitud |
| e215 | Una o varias identidades del interesado ya existen en una solicitud abierta. si actualmente hay otra solicitud abierta para el mismo identity\_value en estado «pending» o «in\_progress». |
| e311 | Tipo de contenido de solicitud inválido |
| e312 | Versión de API inválida |
| e313 | subject\_request\_id inválido |
| e314 | Formato de submitted\_time inválido |
| e315 | Longitud de status\_callback\_url inválida |
| e316 | Formato de status\_callback\_url inválido |
| e317 | Formato de app\_id inválido |
| e318 | identity\_type inválido |
| e319 | La plataforma de aplicación no coincide con los tipos de identidad |
| e321 | Los usuarios de LAT no son compatibles a través de la API |
| e322 | subject\_request\_type inválido |
| e323 | Formato de subject\_identities inválido |
| e324 | Longitud de subject\_identities inválida |
| e325 | Valor subject\_identities inválido |
| e326 | Formato JSON no válido en el cuerpo de la solicitud |
| e411 | AppID es incorrecto o no pertenece a tu cuenta |
| e412 | No hay permisos para cancelar la solicitud de eliminación |
| e413 | No hay permisos para ver la solicitud |
| e511 | Problema interno, espera 60 minutos e intenta nuevamente. Si el problema persiste, contacta con el soporte de AppsFlyer: support@AppsFlyer.com support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## Rasgos y limitaciones

* **Límite de tasa de la API de OpenDSR: 350 solicitudes por minuto**. Superar este límite resultará en un error, lo que requerirá que la solicitud sea reenviada. Mantenerse dentro de este límite de tasa permite hasta 504.000 solicitudes por día.
* Al verificar el estado de una solicitud de hace más de 60 días, se devuelve "solicitud no encontrada".

<div data-zendesk-anchors="privacy-regulations=regulaciones-de-privacidad h_01HB866TQ0AWHQ9659Q8Q4XMQM=regulaciones-de-privacidad the-opendsr-initiative=la-iniciativa-opendsr h_01HB866TQ0R18S4GCH3KPGNJHD=la-iniciativa-opendsr definitions=definiciones h_01HB866TQ06XV2AJDMA3M5Q5KK=definiciones dsr-requirements=requisitos-de-dsr h_01HB866TQ0JNEZTHQ7BR1TMD5M=requisitos-de-dsr appsflyer-gdpr-requests-api=api-de-solicitudes-gdpr-de-appsflyer h_01HB866TQ0HNFGF9QTJNT792N7=api-de-solicitudes-gdpr-de-appsflyer gdpr-request-flow=flujo-de-solicitudes-gdpr h_01HB866TQ0FCZGQ1DWENVSWHSG=flujo-de-solicitudes-gdpr gdpr-request-format=formato-de-solicitudes-gdpr h_01HB866TQ0GC7V1081GT53TWEZ=formato-de-solicitudes-gdpr parameters=par%C3%A1metros h_01HB866TQ0CFAC0X2Y98B4EE5Q=par%C3%A1metros subject_identities-objects=objetos-subject_identities h_01HB866TQ02HMKJMKKPHHR4CMN=objetos-subject_identities example-gdpr-erasure-request=ejemplo-solicitud-de-eliminaci%C3%B3n-de-gdpr h_01HB866TQ1CT316PTFBJC59C79=ejemplo-solicitud-de-eliminaci%C3%B3n-de-gdpr h_01HB866TQ1D7290A6G29Q4HDE7=ejemplo-de-c%C3%B3digo-de-solicitud-de-borrado-gdpr status-request-format=formato-de-solicitud-de-estado h_01HB866TQ1YEZZ4M6QMHTKCEGX=formato-de-solicitud-de-estado status-response-example=ejemplo-de-respuesta-de-estado h_01HB866TQ1M7G7JNH0V7TEVFYY=ejemplo-de-respuesta-de-estado status-postbacks=postbacks-de-estado h_01HB866TQ1109WJ2J13D8FM8KX=postbacks-de-estado validate-postback=validar-postback h_01HB866TQ1YG0B6JDEQ2KMFEN0=validar-postback discovery-response-example=ejemplo-de-respuesta-de-descubrimiento h_01HB866TQ1AJCSS2442EEWA19X=ejemplo-de-respuesta-de-descubrimiento cancellation-response=respuesta-de-cancelaci%C3%B3n h_01HB866TQ1F72KP3S55ZJYC8Y7=respuesta-de-cancelaci%C3%B3n how-does-it-work=c%C3%B3mo-funciona h_01HB866TQ1KFRGX7NZCSJWVW0T=c%C3%B3mo-funciona gdpr-api-return-codes=c%C3%B3digos-de-retorno-de-la-api-de-gdpr h_01HB866TQ128R2TSHS4JTCQK70=c%C3%B3digos-de-retorno-de-la-api-de-gdpr http-return-code-400-bad-request=c%C3%B3digo-de-retorno-http-400-solicitud-incorrecta h_01HB866TQ1A51STZQCJC5TV65X=c%C3%B3digo-de-retorno-http-400-solicitud-incorrecta return-code-400-bad-request-messages=mensajes-de-solicitud-incorrectos-c%C3%B3digo-de-retorno-400 h_01HB866TQ10MAMTS9WB0CKN55V=mensajes-de-solicitud-incorrectos-c%C3%B3digo-de-retorno-400 limitations=rasgos-y-limitaciones h_01HB866TQ1PXGRX5JRHRSCT0EN=rasgos-y-limitaciones" />
