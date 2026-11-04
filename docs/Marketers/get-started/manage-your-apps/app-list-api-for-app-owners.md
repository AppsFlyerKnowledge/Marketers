---
title: API de lista de apps para propietarios de apps
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-08-12T12:04:52Z'
  id: 360011999877
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/360011999877
---
> **En resumen:** Recupera las aplicaciones activas y pendientes asociadas a tu cuenta de AppsFlyer.

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

Si eres una ad network, usa la API de <Anchor target="_blank" href="/partners/es/docs/app-list-api-for-ad-networks">lista de apps para ad networks</Anchor>.

**Más información**: <Anchor target="_blank" href="/marketers/es/docs/about-advertiser-apis">Lista de API para anunciantes</Anchor>

<div id="get-app-list-api" />

## Obtener la API de lista de apps

Las siguientes secciones incluyen la información necesaria para usar la API.

**Obtener los aspectos básicos de la lista de apps**

<div id="get-api-list-basics" />

<Accordion title="Aspectos básicos de la lista de API">

<table><thead><tr><th>Categoría</th><th>Elemento</th><th><span>Nota</span></th></tr></thead><tbody><tr><td rowspan="3">Solicitud</td><td>Método HTTP</td><td><code>GET</code></td></tr><tr><td>Ruta</td><td><span>https://hq1.appsflyer.com/api/mng/apps</span></td></tr><tr><td>Encabezado de autorización </td><td><ul><li>El encabezado de autorización obligatorio contiene un token de portador. </li><li>Un usuario administrador obtiene el token en el Dashboard de la siguiente manera: <a href="./managing-appsflyer-tokens" target="_blank">El administrador va a la lista desplegable de correo electrónico &gt; tokens de API para obtener el token V2.0</a> </li></ul></td></tr><tr><td rowspan="3"> Respuesta</td><td>Resultados</td><td>Devuelve en un JSON</td></tr><tr><td>Límite de solicitud</td><td><ul><li>20 solicitudes/minuto</li><li>100 solicitudes/día</li></ul></td></tr><tr><td>Límite de registros</td><td>1.000 registros/solicitud. Si se van a devolver más de 1.000 registros, usa solicitudes de paginación de seguimiento descritas en este artículo.</td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="Solicitud API">

La solicitud de la API consta del método, la ruta, el parámetro capabilities obligatorio y los parámetros de paginación opcionales. El token se incluye en el encabezado Authorization.

**Emitido**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

Obtener los parámetros obligatorios de la lista de apps:

| Parámetro de consulta | Descripción |
| --- | --- |
|  | No hay parámetros de consulta obligatorios para esta API |

<div id="pagination-mechanism" />

#### **Mecanismo de paginación**

Se ha implementado un mecanismo de paginación, siempre operativo.

**Principios de la paginación:**

* Devuelve hasta 1.000 registros por solicitud (página).
* Los JSON de respuesta contienen las siguientes claves relacionadas con la paginación:
  * **meta.total\_items**: El número de registros que devolverán todas las páginas en conjunto. Esto representa el número de aplicaciones para las que se te han concedido las *capabilities* que se están consultando.
  * Los enlaces de paginación (mostrados en el JSON siguiente) tienen las siguientes claves:
    * **links.prev**: Si hubo una solicitud anterior: la solicitud utilizada para generar la página anterior.
    * **links.self**: La solicitud actual: la solicitud utilizada para generar el JSON (página) actual
    * **links.next**: La solicitud necesaria para obtener la página siguiente. Si no hay ninguna clave *next* , esta es la última página.

**Usa uno de los siguientes métodos de control de la paginación:**

* [Mejores prácticas] Usa los *enlaces* en el JSON: si la clave *links.next* existe, úsala para crear una solicitud para obtener la página siguiente. Sigue haciéndolo hasta que recibas un JSON sin una *links.next* clave.
* Implementa mediante programación los parámetros *limit* y *offset* junto con la clave *total\_items*.

**Ejemplo de JSON de enlaces de paginación**

* El siguiente ejemplo contiene el resultado de la segunda solicitud, que consta de dos registros en la sección de datos (no mostrada).
* El número total de registros que se devolverán es 6.
* La clave **links.next** contiene la solicitud que devuelve la segunda página: los registros 5 y 6.

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

Parámetros del mecanismo de paginación (opcionales):

| Parámetro de consulta | Descripción |
| --- | --- |
| límite | Número de registros que se devuelven en cada llamada<ul><li>Máximo: 1.000</li><li>Si no envías `limit`, se establece automáticamente en 1.000.</li><li>Ejemplo: `limit=2`</li><li>Obligatorio: No</li></ul> |
| offset | El primer registro que se devuelve en la llamada. Los números de registro empiezan en 0.<ul><li>Si no envías `offset`, se establece automáticamente en 0.</li><li>Ejemplo: `offset=2`</li><li>Obligatorio: No</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="Respuesta JSON">

| **Clave** | **Nota** |
| --- | --- |
| ID | ID de la aplicación, por ejemplo: `id123456789`, `com.myapp.com` |
| type | Devuelve siempre `app` |
| conjunto de anuncios | Nombre de aplicación |
| Identificador de origen | iOS o Android |
| moneda | Código de moneda específico de la aplicación |
| time\_zone | Zona horaria específica de la aplicación |
| total\_items | Cantidad de aplicaciones alojadas en la cuenta |
| enlaces | Mecanismo de paginación (explicado en la sección de parámetros)<ul><li>prev: la llamada utilizada para generar la página anterior</li><li>self: la llamada utilizada para generar la página actual</li><li>next: la llamada utilizada para generar la página siguiente</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="Ejemplo de cURL para obtener la lista de aplicaciones y respuesta">

**Solicitud cURL**

Este ejemplo incluye una llamada completa, incluidos los parámetros de paginación opcionales.

```bash
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}' \
```

**Respuesta JSON**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="Códigos de respuesta HTTP">

| Código | Mensaje | Observaciones/resolución de problemas |
| --- | --- | --- |
| 200 | Correcto | Datos válidos devueltos |
| 200 | Correcto | **Síntoma**: No se devuelven datos<br /><br />**Acción**: Asegúrate de que el token de autenticación esté en el encabezado Bearer. |
| 400 | Solicitud incorrecta | Consulta el mensaje incluido en el JSON |
| 401 | No autorizado | **Mensaje**: El token de autorización tiene un formato incorrecto<br /><br />Asegúrate de que tienes el token correcto; el token debe tener más de 700 caracteres. |
| 404 | No encontrado | <ul><li>Resuelve cualquier problema relacionado con la red o con el cortafuegos.</li><li>Asegúrate de que las <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">direcciones IP de AppsFlyer estén en la lista de permitidos</Anchor></li><li>Asegúrate de usar el token emitido más recientemente.</li><li>No se han encontrado datos: no se ha encontrado ninguna aplicación.</li></ul> |
| 429 | Demasiadas solicitudes | Se ha superado el límite de solicitudes |

</Accordion>

<div data-zendesk-anchors="get-app-list-api=obtener-la-api-de-lista-de-apps h_01KQS56KS2G7TD4VHZCHVP0W9S=obtener-la-api-de-lista-de-apps h_01KQS56KS26TY81ACBN2XBK3W2=get-api-list-basics h_01KQS56KS27NETZ4C5RY28V804=api-request pagination-mechanism=mecanismo-de-paginaci%C3%B3n h_01KQS56KS33VFVX099T1S2928G=mecanismo-de-paginaci%C3%B3n h_01KQS56KS3Q5EEVSSC7G1FEFXR=json-response h_01KQS56KS3EZCH1KBBQQKTXWYP=get-app-list-curl-example-and-response h_01KQS56KS3S04KDZ58J7XKQNCK=http-response-codes" />
