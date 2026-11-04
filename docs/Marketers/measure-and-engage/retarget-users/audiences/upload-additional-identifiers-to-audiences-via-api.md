---
title: 'Audiencias: API de identificadores adicionales'
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-07T00:17:57Z'
  id: 4411552670993
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/4411552670993
---
> **De un vistazo:** Utiliza la API de identificadores adicionales de audiencias para cargar masivamente identificadores de usuarios desde tus sistemas internos (como BI y CRM) a AppsFlyer Audiences, lo que permite una comunicación más amplia con socios relevantes basándose en estos identificadores.

<div id="about-the-api" />

## Acerca de la API

La API de identificadores adicionales de audiencias se puede usar para añadir los siguientes identificadores de usuario desde tus sistemas internos a AppsFlyer Audiences:

* Hasta 2 direcciones de correo electrónico cifradas
* Número de teléfono cifrado
* Número de teléfono E164 cifrado

Luego puedes optar por enviar estos identificadores a tus socios de Audiencias (sujeto a tu <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuario a nivel de cuenta</Anchor>), lo que les permitirá identificar de manera más precisa tus audiencias objetivo. Ten en cuenta que no todos los socios publicitarios admiten todos los identificadores.

<div id="when-should-i-use-this-api" />

### ¿Cuándo debo utilizar esta API?

Esta API está diseñada para usarse cuando necesitas cargar un gran volumen de datos de identificadores. Generalmente, esto se refiere a datos recopilados a lo largo del tiempo (por ejemplo, correos electrónicos en formato hash recopilados de todos los usuarios de una aplicación durante los últimos 12 meses). Para actualizaciones individuales en tiempo real de identificadores de dispositivos específicos, <Anchor target="_blank" href="/marketers/es/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">configura identificadores adicionales</Anchor> en el SDK de AppsFlyer o la API S2S-mobile.

<div id="important" />

> 🚧 **¡Importante!**
>
> **Cifrado:** Todos los valores de identificadores adicionales **deben** estar cifrados con hash SHA256. Los identificadores no cifrados no serán procesados.
>
> **Tiempo:** Para asegurar una coincidencia precisa de los identificadores, la API de identificadores adicionales de audiencias puede utilizarse tan pronto como el **día posterior** al reporte de los identificadores clave a través del SDK de AppsFlyer (UTC). Por ejemplo, los identificadores clave reportados el 3 de enero de 2022 (UTC) pueden actualizarse a través de esta API el 4 de enero de 2022 (UTC) o después.

<div id="actions" />

## Acciones

* [Añadir/modificar identificadores](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [Eliminar identificadores](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

<div id="authentication" />

## Autenticación

La solicitud debe incluir un encabezado HTTP que contenga el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token API de AppsFlyer V2.0</Anchor> de tu cuenta. Pide al administrador de tu cuenta que obtenga este token desde el panel de AppsFlyer.

<div id="api-specifications-and-sample-code" />

## Especificaciones de la API y código de ejemplo

<div id="addmodify-identifiers-put" />

<Accordion title="Añadir/modificar identificadores (PUT)">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**URL de solicitud de la API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parámetro | Descripción | Obligatorio |
| --- | --- | --- |
| `{id de la aplicación}` | ID de la aplicación desde la que se recopilaron los identificadores (tal como aparece en el panel de AppsFlyer) | Sí |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**Cuerpo de la solicitud de API**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },  
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| Parámetro | Descripción | Obligatorio |
| --- | --- | --- |
| `{tipo_de_clave}` | El identificador usado como valor único para representar al usuario en cada fila de datos de la solicitud.<br /><br />El valor especificado aquí se aplica a todas las filas de la solicitud.<br /><br />Valores posibles:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>id\_usuario\_cliente</li><li>imei</li><li>oaid</li></ul> | Sí |
| `{acción}` | agregar | No<br /><br />Valor por defecto: agregar |
| `{valor_clave}` | Valor de identificador válido para el tipo de clave especificado | Sí |
| \{identificadores\} | Objeto que contiene los nombres y valores de los identificadores a agregar:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Sí<ul><li>Debe incluir un valor para al menos uno de estos tres identificadores</li></ul> |
| `{hashed_emails}` | Un array de hasta dos direcciones de correo electrónico cifradas<br /><br />Formato:<ul><li>En minúsculas</li><li>Sin espacios en blanco</li><li>Con hash SHA256</li></ul>Valor de ejemplo antes del hash: nombre@dominio.com | No |
| `{phone_number_sha256}` | Número de teléfono (ver nota a continuación)<br /><br />Formato:<ul><li>Sin símbolos, letras ni ceros iniciales</li><li>Incluir código de país</li><li>Con hash SHA256</li></ul>Valor de ejemplo antes del hash:<br /><br />442070313000 | No |
| `{phone_number_e164_sha256}` | Número de teléfono en formato E164 (ver nota a continuación)<br /><br />Formato<ul><li>Número de teléfono E164</li><li>Con hash SHA256</li></ul>Valor de ejemplo antes del hash:<br /><br />+442070313000 | No |

<div id="notes" />

> 📘 **Notas**
>
> * Diferentes socios publicitarios admiten distintos formatos de números de teléfono. Por lo tanto, si decides añadir un número de teléfono, se recomienda enviar ambos identificadores: *phone\_number\_sha256* y *phone\_number\_e164\_sha256*.
> * `customer_user_id` es el mismo identificador al que se hace referencia en otras partes de esta sección como CUID (ID de usuario de cliente). Cuando `key_type` es `customer_user_id`, usa el valor de CUID de la cuenta como `key_value`. Consulta la <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuario de audiencias</Anchor> para obtener más información sobre este tema y otros identificadores compatibles.

**Restricciones**

Las siguientes restricciones se aplican a la solicitud **Agregar/modificar identificadores**:

* Los valores existentes previamente (si los hay) serán sobrescritos por los valores enviados en la solicitud.
* El objeto `{data}` puede incluir un máximo de 4000 filas (key\_values) por solicitud.

**Solicitud de ejemplo para agregar identificadores**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="Eliminar identificadores (PUT)">

**URL de solicitud de la API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parámetro | Descripción | Obligatorio |
| --- | --- | --- |
| `{id de la aplicación}` | ID de la aplicación desde la que se recopilaron los identificadores (tal como aparece en el panel de AppsFlyer) | Sí |

**Cuerpo de la solicitud de API**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| Parámetro | Descripción | Obligatorio |
| --- | --- | --- |
| `{tipo_de_clave}` | El identificador usado como valor único para representar al usuario en cada fila de datos de la solicitud.<br /><br />El valor especificado aquí se aplica a todas las filas de la solicitud.<br /><br />Valores posibles:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>id\_usuario\_cliente</li><li>imei</li><li>oaid</li></ul> | Sí |
| `{valor_clave}` | Valor de identificador válido para el tipo de clave especificado | Sí |
| `{acción}` | eliminar | No<br /><br />Valor por defecto: agregar |
| \{identificadores\} | Un array que contiene los nombres de los identificadores cuyos valores deben eliminarse:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Sí<ul><li>Debe incluir al menos uno de estos tres identificadores</li></ul> |

**Restricciones**

El objeto `{data}` puede incluir un máximo de 4000 filas (key\_values) por solicitud.

**Solicitud de ejemplo para eliminar identificadores**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="Respuestas">

| Código | Mensaje | Descripción |
| --- | --- | --- |
| 202 | Aceptado para su procesamiento | La solicitud se aplicará en la siguiente ventana de procesamiento. |
| 400 | El cuerpo de la solicitud debe incluir un tipo de clave válido | Los siguientes tipos de clave son compatibles:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>id\_usuario\_cliente</li><li>imei</li><li>oaid</li></ul> |
| 400 | La solicitud debe contener 'datos' con al menos un elemento | La lista de datos no puede estar vacía. |
| 400 | La solicitud de 'datos' no debe superar los 4000 en una sola petición | La lista de datos puede contener un máximo de 4000 filas. |
| 400 | Los datos pedidos contienen demasiados elementos 'datos' no válidos | Más del 10% de los datos a modificar no son válidos según lo especificado. |
| 404 | AppsFlyer - Página no encontrada | Verifique que:<ul><li>El `{app-id}`, tal como se especifica en la URL de la solicitud de API, es correcto.</li><li>El encabezado HTTP contiene el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token API de AppsFlyer V2.0</Anchor> correcto. El administrador de su cuenta puede obtener este token en el panel de control de AppsFlyer.</li></ul> |

**Ejemplos de respuestas**

```json
{
"message": "Aceptado para su procesamiento",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "El cuerpo de la solicitud debe tener un key_type válido",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "La solicitud debe tener 'data' con al menos 1 elemento",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Los datos de la solicitud no deben superar el tamaño de 4000 en una sola solicitud",
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Los datos de la solicitud tienen demasiados elementos 'data' no válidos",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="Limitaciones de tasa">

* 5 solicitudes por segundo
* 350 solicitudes por minuto

</Accordion>

<div data-zendesk-anchors="api-overview=acerca-de-la-api h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=acerca-de-la-api when-should-i-use-this-api=cu%C3%A1ndo-debo-utilizar-esta-api h_01HNZP1Y2MJY56TMN6QH4BVRPA=cu%C3%A1ndo-debo-utilizar-esta-api h_01HNZP1Y2MX414NJ49BCVW7KZC=importante methods=acciones h_01HNZP1Y2MS5V43XS008GG4S32=acciones authentication=autenticaci%C3%B3n h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=autenticaci%C3%B3n api-specifications-and-sample-code=especificaciones-de-la-api-y-c%C3%B3digo-de-ejemplo h_01HNZP1Y2MR0GCCA1916RMB6GJ=especificaciones-de-la-api-y-c%C3%B3digo-de-ejemplo h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=notas h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
