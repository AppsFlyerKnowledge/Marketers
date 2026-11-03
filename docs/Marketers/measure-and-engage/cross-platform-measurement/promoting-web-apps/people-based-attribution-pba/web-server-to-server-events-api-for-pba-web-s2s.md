---
title: API de eventos web de servidor a servidor para PBA (Web-S2S)
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
  edited_at: '2026-08-12T12:11:54Z'
  id: 360006997298
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360006997298
---
> **De un vistazo:** Utilice la API web de servidor a servidor (Web-S2S) para reportar eventos y conversiones a PBA que no son notificados por el SDK Web.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

## API de eventos web de servidor a servidor para PBA

La API Web-S2S para la atribución basada en personas complementa el <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide">SDK</Anchor> web, lo que permite a los marketers reportar los eventos que se producen en sus sitios web pero que quedan fuera del ámbito del SDK web. Por ejemplo, un visitante del sitio web (un usuario web), dispara un evento de pago en línea, procesado por sistemas backend. Tras el procesamiento, el backend, utilizando la API S2S, reporta el evento a AppsFlyer.

Los eventos enviados por la API S2S:

* se registran de forma similar a los eventos reportados por el SDK web,
* se incluyen en los paneles de control de PBA si se establecen como eventos de conversión,
* rellenan el raw data de PBA con el *campo event\_source* configurado como *web S2S*.

## Instrucciones de uso de la API

Crea tu llamada a la API utilizando las secciones siguientes.

| N.º | Elemento | Observaciones |
| --- | --- | --- |
| 1 | ID de usuario único | <ul><li>Intenta proporcionarnos el mejor ID de usuario único disponible. Esto tiene un impacto significativo en el análisis de datos.</li><li>La práctica recomendada es enviar el customerUserId. Si no está disponible, envía el afUserId, que es el ID de cookie del sitio web establecido por WebSdk.</li><li>En el momento en que asocies tu ID de usuario de cliente<Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">(CUID</Anchor>) con el [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid) envía un mensaje setCuID() con ambos ID.</li></ul> |
| 2 | Marca de tiempo | <ul><li>AppsFlyer aplica una validación estricta a las marcas de tiempo de los eventos entrantes:</li></ul><ul><li>**Eventos que llegan con retraso:** Los eventos se aceptan con su marca de tiempo original si llegan en las 24 horas posteriores al día al que pertenecen. **Por ejemplo**, un evento con una marca de tiempo del lunes (2025-08-18 23:59 UTC) conservará esa marca de tiempo si se envía **en cualquier momento hasta el martes** a las 23:59:59 UTC. Si el mismo evento se envía después del martes a las 23:59:59 UTC, la marca de tiempo se sobrescribe con la hora de recepción del servidor.</li><li>**Marcas de tiempo futuras:** No se permiten eventos con una marca de tiempo posterior a la hora de llegada real. Estas marcas de tiempo también se sobrescriben con la hora de recepción del servidor.</li></ul><ul><li>Las marcas de tiempo se basan en UTC. Si es necesario, convierte la hora local en hora UTC antes de rellenar el parámetro.</li></ul> |
| 3 | Ingresos y divisas | Debes rellenar *eventRevenueCurrency* y *eventRevenue* incluso si están incluidos en eventValue. Hazlo porque los utilizamos en nuestros paneles de control. |

<div id="api-basics" />

<Accordion title="Conceptos básicos de la API">

La implementación de la API requiere las siguientes credenciales disponibles en el panel de control:

* ID de paquete (también conocido como ID del paquete de marca)
* Clave de desarrollador web

**Para obtener las credenciales:**

1. En AppsFlyer, en el menú superior, selecciona **Mis aplicaciones** > **Ver paquetes de marcas**.  
   Aparece la lista de paquetes.
2. Copia y registra lo que corresponda:
   * ***ID de paquete de marca***
   * ***Clave de desarrollador web***

#### Conceptos básicos de la API Web S2S

| Ruta | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`: es el ID del paquete de aplicaciones disponible en el panel de control.</li><li>`method` es uno de los siguientes:<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): se envía para eventos de backend reportables</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) se envía al asociar afUserId con tu CUID</li></ul></li></ul> |
| --- | --- |
| Método HTTP | `POST` |
| Tipo de contenido aceptado | `application/json` |
| Limitación de la carga útil de JSON | Tamaño de la carga útil de JSON: máximo 1 KB |
| Limitación de la tasa | Volumen de limitación POST: 60 000 POST por minuto. Para aumentar el límite, contacta a tu CSM. |
| TLS | <ul><li>TLS 1.2 o posterior</li><li><Anchor target="_blank" href="/marketers/es/docs/appsflyer-https-ssl-encryption-policy-support#mensajes-salientes-appsflyer-como-cliente">cifrados compatibles</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="Método setCuId">

| Nombre del método | setCuId |
| --- | --- |
| Caso de uso | Al asociar un CUID a un visitante de tu sitio web. Por ejemplo, cada vez que hagas coincidir el `afUserId` web con tu ID de usuario de cliente. De este modo, la PBA puede cotejar datos de diversas fuentes. Esto es similar a <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> en el sitio web. |
| Ruta del método | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Carga útil | La carga útil de JSON consta de los parámetros que se enumeran a continuación. Todos los parámetros son obligatorios.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

#### Ejemplo de setCuId de Curl

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

<Accordion title="Método del evento">

| Nombre del método | event |
| --- | --- |
| Caso de uso | Envío |
| Ruta del método | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Información detallada | La sección [Detalles del método Event](/docs/web-server-to-server-events-api-for-pba-web-s2s#detalles-del-método-event) de este artículo contiene detalles sobre la carga útil, un ejemplo de Curl, un ejemplo de Python y sugerencias de pruebas. |

</Accordion>

## Detalles del método Event

<div id="payload-parameters" />

<Accordion title="Parámetros de carga útil">

Los parámetros de carga útil se dividen en identificadores de usuario y parámetros de evento.

* ID de usuario: debes enviar al menos un parámetro de ID de usuario.
* Evento: envía los parámetros obligatorios y los parámetros opcionales según sea necesario.

#### Parámetros de identificador de usuario (envía al menos un parámetro)

| Parámetro de ID de usuario | Descripción |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | El <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario del cliente (CUID)</Anchor> es un identificador único establecido por ti.<ul><li>Usa el mismo identificador para los eventos reportados por cualquier medio a AppsFlyer. Esto significa que se utiliza el mismo identificador en el SDK web, el SDK móvil y las API S2S.</li><li><Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">ID de usuario del cliente del SDK web</Anchor></li><li>Formato: cadena</li><li>Ejemplo: `"customerUserId" : "663274"`</li><li>Rellena el campo de raw data: `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | El ID de usuario único asignado por el SDK web a cada usuario que visita tu sitio web. Deberás transmitir el valor de la cookie a tus servidores de backend.<ul><li>Detalles de la cookie:<ul><li>Nombre: afUserId</li><li>Valor: establece *afUserId* a este valor</li><li>Dominio: website-domain</li></ul></li><li>Ejemplo: `"afUserId" : "unique_cookie_uuid"`</li><li>Rellena el campo de raw data: `af_web_id`</li></ul> |

#### Parámetros del evento

| Nombre de parámetro | Obligatorio | Descripción |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | Sí | Rellénalo utilizando la [clave de desarrollador web](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) disponible en el panel de control.<ul><li>Ejemplo:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | Sí | Identificador de atributo de evento para uso interno de AppsFlyer. Siempre ajustado en *EVENT.*<ul><li>Ejemplo: `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | Sí | <ul><li>Utilizamos este parámetro para diferenciar los eventos de conversión de los que no lo son utilizando la <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#web-event-settings">lista de conversión de eventos</Anchor> establecida por el marketer en los ajustes de PBA.</li><li>Asegúrate de rellenarlo con valores coherentes con la lógica de conversión del marketer.</li><li>Formato: cadena</li><li>Ejemplo: `"eventName" : "web_purchase"`</li><li>Rellena el campo de raw data: `event_name`</li></ul> |
| <span id="timestamp"></span>timestamp | No | Hora en que se produjo el evento en milisegundos. Se envía como una <Anchor target="_blank" href="https://www.unixtimestamp.com/">marca de tiempo Unix</Anchor> de 13 dígitos.<ul><li>Si no se envía ninguna marca de tiempo, la hora se establece utilizando la hora del servidor.</li><li>**Los eventos que llegan con retraso se registran con la hora actual del servidor.** Por "retraso" se entiende la llegada después de la medianoche UTC del día siguiente al evento. Por ejemplo, un evento que se produzca el lunes **debe** procesarse antes de la medianoche UTC del martes.</li><li>Los eventos que tienen una marca de tiempo en el futuro (relativa a la hora actual del servidor) se marcan con la hora del servidor.</li><li>Formato: Int</li><li>Ejemplo: `"timestamp" : 1584835200123`</li><li>Rellena el campo de raw data: `event_time`</li></ul> |
| <span id="eventvalue"></span>valor del evento | No | Asignación de parámetros del evento que describen el evento. Utiliza este parámetro para enviar eventos in-app enriquecidos, como el SKU del producto y el precio del artículo.<ul><li>**¡Nota sobre los ingresos!** **Nota sobre los ingresos:** Puedes rellenar este parámetro con los detalles de los ingresos. Además, debes rellenar *eventRevenue* y *eventRevenueCurrency.*</li></ul><ul><li>Formato: JSON</li><li>Ejemplo: Para enviar el SKU ABC123, de color azul y con un precio unitario de $3,99, configura eventValue como:<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>Limitación: 1000 caracteres. Si excedes el límite, se truncará.</li><li>Rellena el campo de raw data: `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | No | Código de moneda de un evento de ingresos, como código de moneda <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> de tres caracteres.<ul><li>Valor predeterminado: USD</li><li>Formato: cadena</li><li>Ejemplo:  `"eventRevenueCurrency" : "EUR"`</li><li>Rellena el campo de raw data: `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | No | Ingresos (valor monetario) asignados a un evento.<br /><br />**¡Atención!** Nota: **Si los ingresos se reportan en *eventValue,* indícalo también en *eventRevenue* y rellena eventRevenueCurrency.**<ul><li>Se admiten valores negativos. Por ejemplo, un reembolso.</li><li>Formato: flotante</li><li>Valores de ejemplo: `1``1.2``1234.20``-1234.20`</li><li>Rellena el campo de raw data: `event_revenue`</li></ul> |
| <span id="eventcategory"></span>eventCategory | No | Este parámetro está obsoleto y se eliminará del sistema en el futuro. Utiliza eventValue en su lugar. |
| <span id="eventlabel"></span>eventLabel | No | Este parámetro está obsoleto y se eliminará del sistema en el futuro. Utiliza eventValue en su lugar. |
| <span id="referrer"></span>referrer | No | Referente HTTP<ul><li>Formato: cadena</li><li>Ejemplo:`"referrer" : "https://www.google.com/"`</li><li>Rellena el campo de raw data: `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | No | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">Solicitud de agente de usuario</Anchor> enviada por el navegador al servidor.<ul><li>Siempre que sea posible, envía este valor, ya que ayuda a determinar el tipo de dispositivo.</li><li>Formato: cadena</li><li>Ejemplo: `"userAgent" : "Chrome/80.0.3987"`</li><li>Rellena el campo de raw data: `user_agent`</li></ul> |
| <span id="ip"></span>ip | No | Dirección IP del usuario<ul><li>Cuando sea posible, envía el valor de este campo. Ayuda a determinar la <Anchor target="_blank" href="/marketers/es/docs/determine-user-location">geolocalización</Anchor> del usuario.</li></ul><ul><li>Formato: cadena</li><li>Ejemplo: `"ip": "192.0.2.1"`</li><li>Rellena el campo de raw data: `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Ejemplo de Curl">

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

<Accordion title="Ejemplo de Python">

```python
''' usando el paquete requests de Python, instálalo con pip install requests  '''
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

<Accordion title="Pruebas">

A modo de prueba, envía varios eventos como se indica a continuación:

1. Envía un evento.
2. Asegúrate de obtener un código de retorno 200 OK. Si no es así, tome medidas correctivas utilizando los códigos de retorno y los mensajes de error.
3. Espere varias horas después de medianoche UTC para ver el evento reportado en el raw data de PBA. Debes esperar porque los datos de PBA se procesan una vez al día.

</Accordion>

## Información adicional

<div id="getting-the-web-dev-key" />

<Accordion title="Obtener la clave de desarrollador web">

**Para obtener la clave de desarrollador web:**

1. En AppsFlyer, ve a la sección ***Mis aplicaciones***.
2. Haz clic en Ver paquetes de marca.

   [![GetWebDevKeyPba_us-en.pn](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)
3. Copia la ***clave de desarrollador web*** requerida.

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Extraer el afUserID del SDK web">

* El `afUserId` es un identificador único, establecido por el SDK web cuando un usuario visita tu sitio por primera vez.
* Si necesitas el `afUserId`, utiliza uno de los métodos que se indican a continuación.

#### **Obtener el afUserId del encabezado de la cookie HTTP**

* El `afUserId` es enviado por el navegador del visitante cuando visita tu sitio web.
* Extráelo del encabezado de la cookie HTTP si es necesario.

#### **Ver el afUserId en el navegador del visitante**

* Visualiza el `afUserId` en el navegador del visitante, con fines de solución de problemas y depuración.
* Para que esté disponible, el visitante tiene que haber visitado primero una página que tenga el SDK web al menos una vez.
* La cookie que contiene `afUserId` es una cookie de origen en relación con tu dominio.
* El procedimiento que sigue se preparó utilizando Chrome 81. Puede haber algunas diferencias entre los distintos navegadores y sistemas operativos.

**Para obtener el afUserId del navegador del visitante:**

1. En tu navegador, ve a tu sitio web.
2. Haz clic con el botón derecho del ratón y selecciona ***Inspeccionar***Se abre la ventana de inspección de elementos del navegador.

   [![S2S_inspect.jpg](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)
3. Ve a la pestaña (A) ***Aplicación***.
4. En el menú lateral, (B) expande Cookies.
5. Selecciona tu sitio web. Si no aparece, actualiza el navegador.
6. En el (C) ***filtro***, introduce `afUserId`  
   Se muestra el valor de afUserID.

</Accordion>

<div id="response-codes" />

<Accordion title="Códigos de respuesta">

| Código de respuesta | Mensaje | Cómo manejarlo |
| --- | --- | --- |
| 200 | Correcto |  |
| 404 | No se encuentra | <ul><li>Comprueba el punto de conexión</li><li>Comprueba que el ID del paquete es correcto</li></ul> |
| 400 | Solicitud incorrecta | <ul><li>Hay un error en el JSON. Consulta el mensaje de error para obtener más información.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolución de problemas">

* Síntoma: Los códigos de retorno HTTP no se devuelven  
  Solución: Agregar los servidores de AppsFlyer a la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">lista de permitidos</Anchor>

</Accordion>

<div id="release-notes" />

<Accordion title="Notas de la versión">

<table><caption>Notas de la versión del SDK web</caption><thead><tr><th>Fecha </th><th>Versión del punto de conexión\*</th><th>Notas</th></tr></thead><tbody><tr><td>12-05-2020</td><td>1</td><td> Lanzamiento inicial</td></tr><tr><td>24-05-2020</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* El número de versión se refiere al número de versión del punto de conexión. <code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=api-de-eventos-web-de-servidor-a-servidor-para-pba h_01HKW2YAW4HHYK27F41HC3B24Y=api-de-eventos-web-de-servidor-a-servidor-para-pba api-use-instructions=instrucciones-de-uso-de-la-api h_01HKW2YAW4DCESP3MNY9D4GTFK=instrucciones-de-uso-de-la-api h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=conceptos-b%C3%A1sicos-de-la-api-web-s2s h_01HKW2YAW4XDKZ3YGAHAP3AG2T=conceptos-b%C3%A1sicos-de-la-api-web-s2s h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=ejemplo-de-setcuid-de-curl h_01HKW2YAW5SJFKGTNRGRKN6NCJ=ejemplo-de-setcuid-de-curl h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=detalles-del-m%C3%A9todo-event h_01HKW2YAW53H43SCYTDXAYBDHX=detalles-del-m%C3%A9todo-event h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=par%C3%A1metros-de-identificador-de-usuario-env%C3%ADa-al-menos-un-par%C3%A1metro h_01HKW2YAW5RR4Q2PCWC9717ACG=par%C3%A1metros-de-identificador-de-usuario-env%C3%ADa-al-menos-un-par%C3%A1metro event-parameters=par%C3%A1metros-del-evento h_01HKW2YAW5G46ZV4Z0CYEWB011=par%C3%A1metros-del-evento h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=informaci%C3%B3n-adicional h_01HKW2YAW5D4N3SYA625F10YFW=informaci%C3%B3n-adicional h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=obtener-el-afuserid-del-encabezado-de-la-cookie-http h_01HKW2YAW5FK04C3AWCXGP1XAW=obtener-el-afuserid-del-encabezado-de-la-cookie-http viewing-afuserid-in-the-visitors-browser=ver-el-afuserid-en-el-navegador-del-visitante h_01HKW2YAW5CT2WZ229KJD2FWYK=ver-el-afuserid-en-el-navegador-del-visitante h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
