---
title: >-
  Plataforma de colaboración de datos (DCP) - Prepara la medición de la
  colaboración
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-01-27T08:47:05Z'
  edited_at: '2026-08-12T11:53:23Z'
  id: 32144170371985
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/32144170371985
---
> **En resumen:** Aprende a crear fuentes de datos de medición y a proporcionar acceso a ellas de forma que puedan ser digeridas por el trabajo de atribución.

## Nota

El primer paso para establecer el proceso de medición es preparar las tres entradas que lo alimentan: conversiones, engagements y mapeo de campaña. Estas entradas deben prepararse basándose en el esquema predefinido o en la estructura de eventos, dependiendo del modo de suministro de datos: eventos in-app o archivos fuente personalizados.

Cuando el modo de provisión es archivos de origen personalizados, el trabajo de atribución se activa automáticamente cuando se suben a la nube las carpetas de conversión y registro de engagement necesarias. En el modo de eventos in-app, el trabajo se activa cuando se seleccionan los eventos in-app relevantes.

## Preparar eventos in-app

Puedes enviar datos de conversión y engagement a través de eventos in-app enviados por el SDK de AppsFlyer integrado en tu aplicación.

> 📘 **Nota:**
>
> Si ya estás pasando eventos in-app de AppsFlyer a través del SDK o a través de solicitudes server-to-server, esta opción podría ser más fácil de implementar que la opción de archivo de origen personalizado.

<div id="prepare-conversion-inapp-events" />

<Accordion title="Preparar eventos in-app de conversión">

El evento in-app de conversión debe incluir la información SKU. En el siguiente ejemplo, la clave `af_order_info` identifica la información SKU:

```
"event_value": {
    "af_currency": "EUR",
    "af_content": "retail",
    "af_order_id": "637f7c400f0e3fddd9e5bcbc",
    "af_order_info": [
        {
            "sku": "a",
            "revenue": 1.1,
            "qty": 2
        },
        {
            "sku": "b",
            "revenue": 100.5,
            "qty": 1
        }
    ]
}
```

Para obtener información sobre cómo preparar eventos in-app, consulta la sección [Crear eventos in-app](#create-inapp-events).

</Accordion>

<div id="prepare-engagement-inapp-events" />

<Accordion title="Preparar eventos in-app de engagement">

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement">Las campañas on-site</Anchor> pueden recibir engagements a través de eventos in-app. El evento in-app de engagement debe incluir los datos de atribución en la clave `event_value`. Mira, como ejemplo, la siguiente estructura JSON `event_value`:

```
"event_value": {
    "media_source": "onsite",
    "campaign_name": "winter_bags",
    "campaign_id": "637f7c400f0e3fddsdfaafe33",
    "engagement_type": "click"
}
```

Puedes utilizar los siguientes campos en tu clave JSON `evant_value`:

| **Campo** | **Descripción** | **Obligatorio** | **Disponible en el esquema de eventos in-app** | **Tipo** |
| --- | --- | --- | --- | --- |
| `id_campaña` | ID de campaña | Sí | No | `string` |
| `campaign_name` | Nombre de la campaña | No | No | `string` |
| `tipo_de_engagement` | Diferencia entre clics e impresiones | Sí | No | `string` |
| `fuente_de_medios` | Fuente de medios atribuida a un evento o restringida (<Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">ver más</Anchor>) | Sí | No | `string` |
| `id_adset` | ID del anuncio | No | No | `string` |
| `ad_name` | Nombre del anuncio | No | No | `string` |
| `ad_type` | Ejemplo: banner, pie de página | No | No | `string` |
| `id_anuncio` | ID del conjunto de anuncios, identificando un grupo que contiene uno o más anuncios | No | No | `string` |
| `adset_name` | Nombre del conjunto de anuncios, identificando un grupo que contiene uno o más anuncios | No | No | `string` |
| `channel` | Canal de fuente de medios. Ejemplo: YouTube para Google, Instagram para Meta Ads | No | No | `string` |

Para más información sobre cómo preparar eventos in-app, consulte la sección Crear eventos in-app.

</Accordion>

<div id="create-inapp-events" />

<Accordion title="Crear eventos in-app">

Para proporcionar datos de conversión y engagement a través de eventos in-app, configura el SDK de AppsFlyer integrado en tu aplicación. Para más información sobre la creación de eventos in-app, consulta:

* <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">Resumen de eventos in-app</Anchor>
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">Implementación de eventos in-app en el SDK de AppsFlyer para desarrolladores</Anchor>

</Accordion>

## Preparar archivos fuente personalizados

Si está realizando una [campaña on-site](#onsite-and-offsite-campaign-measurement), puedes utilizar archivos de origen personalizados como fuente de tus conversiones y engagement con el esquema que se indica en las tablas a seguir.

<div id="the-conversion-source-scheme" />

<Accordion title="Utiliza el esquema de la tabla a seguir para crear un archivo fuente personalizado de conversión:">

Utiliza el esquema de la tabla a seguir para crear un archivo fuente personalizado de conversión.   
El esquema de conversión es único para los tipos de campaña off-site y on-site, y para los distintos Partners de medios.

#### Partners de medios seleccionados:

**G**: Google

**M**: Meta

#### Colores de fondo:

      Campos obligatorios

      Campos recomendados

      Se requiere cualquiera de los campos seleccionados

      Los campos se someten a Hashing según las reglas especificadas por SRN.

<table><colgroup><col/><col/><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th>Categoría</th><th>Parámetro</th><th>Descripción</th><th>Tipo de valor esperado</th><th>CMN</th><th colspan="4">Socios de medios</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th colspan="2">Submotivo de bloqueo</th><th colspan="2">Web</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th>G</th><th>M</th><th>G</th><th>M</th></tr></thead><tbody><tr><td>Requerido</td><td>Ingresos asociados al SKU en la moneda indicada en el campo <code>event_revenue_currency</code>.</td><td>Identificador único del evento.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>nombre_del_evento</td><td>Nombre o tipo del evento (por ejemplo, "purchase", "clic").</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_time</td><td>Marca de tiempo de cuándo ocurrió el evento.</td><td>datetime</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Información de la app</td><td>id_aplicación</td><td>Un ID de usuario de aplicación único establecido por el propietario de la aplicación.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>nombre_aplicación</td><td>Nombre de la aplicación.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>version_app</td><td>Número de versión de la aplicación.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Validaciones de datos</td><td>facebook_browser_id</td><td>Identificador único para el tracking del navegador de Facebook.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_cookie</td><td>Identificador de clic para la atribución de anuncios de Facebook.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>gbraid</td><td>Identificador de atribución de anuncios de Google.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>google_click_id</td><td>ID único para el tracking de clics de anuncios de Google.</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>wbraid</td><td>Identificador de atribución web de Google.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_id</td><td>Identificador único para el tracking de TikTok.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Datos de la campaña</td><td>id_campaña</td><td>Identificador único de la campaña de marketing.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>install_id</td><td>Identificador del evento de instalación de la app.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Datos de conversión</td><td>sku</td><td>SKUs de los productos implicados en la conversión.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_quantity</td><td>Identificador único de un producto (SKU).</td><td>General</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_revenue</td><td>Cantidad del SKU comprado o implicado.</td><td>decimal</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>ingresos_evento</td><td>Valor de ingresos utilizando la moneda de ingresos del evento.</td><td>decimal</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_currency</td><td>Moneda del importe de los ingresos.</td><td>decimal</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Cadena</td><td>client_ip</td><td>Dirección IP del usuario o del dispositivo.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>agente_de_usuario_del_cliente</td><td>Cadena de agente de usuario del dispositivo o navegador del usuario.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>categoría_del_dispositivo</td><td>Categoría del dispositivo del usuario (por ejemplo, móvil, escritorio).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>platform (os?)</td><td>Sistema operativo del dispositivo del usuario (por ejemplo, iOS, Android).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>versión_sistema_operativo</td><td>Versión del sistema operativo del dispositivo.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>ID de usuario</td><td>advertising_id</td><td>Identificador único para fines publicitarios (por ejemplo, IDFA).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>appsflyer_id</td><td>Identificador único de la aplicación en AppsFlyer.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>android_id</td><td>Identificador único del dispositivo Android.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfa</td><td>Establecido por el anunciante</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfv</td><td>ID de proveedor proporcionado por iOS</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>client_id</td><td>Identificador único de cliente (p. ej., generado por el sistema).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_client_id</td><td>no se han especificado reglas</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_client_id</td><td>recortar espacios, convertir a minúsculas</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>cookie</td><td>Datos de cookies del navegador para el tracking de usuario/sesión.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>first_name</td><td>Nombre del usuario.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>last_name</td><td>Apellido del Usuario.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>phone_number</td><td>Número de teléfono del Usuario.</td><td>entero</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>date_of_birth</td><td>Fecha de nacimiento del Usuario.</td><td>datetime</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>género</td><td>Sexo del Usuario.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>Indicador de atribución AF</td><td>Idioma o configuración regional preferidos del Usuario.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>correo electrónico</td><td>Dirección de correo electrónico del Usuario.</td><td>string</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_email</td><td>recortar, convertir a minúsculas, eliminar puntos de las direcciones de correo electrónico de Google</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>teléfono_con_hash_de_tiktok</td><td>E164</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>correo_electrónico_con_hash_de_google</td><td>recortar, convertir a minúsculas, eliminar puntos de las direcciones de correo electrónico de Google</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>teléfono_con_hash_de_google</td><td>E164</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>nombre_con_hash_de_google</td><td>recortar, en minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>apellido_con_hash_de_google</td><td>recortar, en minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>correo_electrónico_con_hash_de_facebook</td><td>recortar, en minúsculas</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>teléfono_con_hash_de_facebook</td><td>formato personalizado (¿sin +?)</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_first_name</td><td>todo en minúsculas, sin puntuación</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_last_name</td><td>todo en minúsculas, sin puntuación</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_date_of_birth</td><td>AAAAMMDD</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_gender</td><td>se recomienda f/m, pero cualquier valor con Hashing es válido</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>Atributos de usuario</td><td>att_status</td><td>Estado de App Tracking Transparency (ATT) para el consentimiento del usuario.</td><td>string</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>Cadena</td><td>Información del dispositivo</td><td>Región geográfica del usuario.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>Ingresos por eventos en USD</td><td>Ciudad asociada al usuario.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>state</td><td>Estado o provincia del Usuario.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>código_de_país</td><td>Código ISO del país del Usuario.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>zip_code</td><td>Código postal/ZIP del Usuario.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>calle</td><td>Dirección postal del Usuario (si está disponible).</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_street</td><td>recortar, en minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_city</td><td>en minúsculas, sin signos de puntuación, sin espacios</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_state</td><td>ANSI para EE. UU., en minúsculas, sin puntuación y sin espacios</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_zip_code</td><td>reglas especiales para EE. UU./Reino Unido, en minúsculas, sin puntuación y sin espacios</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_country_code</td><td>Código de país utilizando ISO 3166 (alpha-2).</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>Datos de referencia/tráfico</td><td>referrer_url</td><td>URL del sitio que remitió al usuario a la página actual.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr><tr><td> </td><td>source_url</td><td>URL de la fuente donde el usuario interactuó por primera vez con la campaña.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr></tbody></table>

</Accordion>

<div id="the-engagement-source-scheme" />

<Accordion title="Obligatorio en la fuente de datos personalizada">

Utiliza el siguiente esquema para crear la fuente de datos de engagement.

> 📘 **Nota:**
>
> Los campos de información personal identificable (PII) asignados en el esquema de fuentes de engagement deben tener una intersección no vacía con los PIIs asignados en el esquema de fuentes de conversión anterior.

| **Campo** | **Descripción** | Obligatorio | **Tipo de valor esperado** |
| --- | --- | --- | --- |
| `appsflyer_id` | ID único generado por el SDK cuando se instala la aplicación | Campo PII opcional. Uno de los campos PII es obligatorio. | `string` |
| `cuid` | ID de usuario único de la aplicación establecido por el propietario de la aplicación | Campo PII opcional. Uno de los campos PII es obligatorio. | `string` |
| `idfa` | ID de publicidad que el usuario puede restablecer en dispositivos iOS. Si no está disponible, se rellena con ceros | Campo PII opcional. Uno de los campos PII es obligatorio. | `string` |
| `idfv` | ID de proveedor proporcionado por iOS | Campo PII opcional. Uno de los campos PII es obligatorio. | `string` |
| `id_aplicación` | Identificador único de la aplicación en AppsFlyer. Ejemplo: iOS: `id123456789` Android: `com.appsflyer.referrersender` | Opcional | `string` |
| `id_campaña` | ID de campaña | Obligatorio | `string` |
| `campaign_name` | Nombre de la campaña | Opcional | `string` |
| `fuente_de_medios` | Fuente de medios atribuida a un evento o restringida (<Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">ver más</Anchor>) | Obligatorio | `string` |
| `tipo_de_engagement` | Diferencia entre clics e impresiones | Obligatorio | `string` |
| `nombre_del_evento` | Establecido por el anunciante | Obligatorio | `string` |
| `event_time` | Hora del evento redondeada a la hora más cercana | Obligatorio | `datetime` |
| `nombre_aplicación` | Establecido por el anunciante | Opcional | `string` |
| `version_app` | Establecido por el anunciante | Opcional | `string` |
| `id_adset` | ID del anuncio | Opcional | `string` |
| `ad_name` | Nombre del anuncio | Opcional | `string` |
| `ad_type` | Ejemplo: banner, pie de página | Opcional | `string` |
| `id_anuncio` | ID del conjunto de anuncios, identificando un grupo que contiene uno o más anuncios | Opcional | `string` |
| `adset_name` | Nombre del conjunto de anuncios, identificando un grupo que contiene uno o más anuncios | Opcional | `string` |
| `channel` | Canal de fuente de medios. Ejemplo: YouTube para Google, Instagram para Meta Ads | Opcional | `string` |
| `Identificador de origen` | Plataforma del dispositivo: iOS, Android o Windows Mobile | Opcional | `string` |

</Accordion>

Para más información sobre cómo preparar fuentes y cargarlas en tu servicio en la nube, consulta la sección [Crear y conectar fuentes de datos personalizadas](#crear-y-conectar-fuentes-de-datos-personalizadas) de este documento.

## Preparar la fuente de mapeo de la campaña

La fuente de tus datos de mapeo de campaña es un archivo de fuente de datos personalizado con el esquema descrito en la tabla a seguir.

> 📘 **Nota:**
>
> Recomendamos utilizar un único archivo de asignación para todas las colaboraciones, ya que es más fácil de mantener y actualizar.

<div id="the-campaign-mapping-scheme" />

<Accordion title="El esquema de mapeo de la campaña">

Utiliza el siguiente esquema para crear la fuente de mapeo de campañas.

| **Tipo de dato** | **Obligatorio** | **Valor esperado** | **Descripción** |
| --- | --- | --- | --- |
| collaborator\_name | Sí | string | El nombre del colaborador con el que trabajas. |
| collaborator\_id | Sí | string | Un identificador único para el colaborador. |
| id\_campaña | Sí | string | El identificador único de la campaña. |
| conversion\_targets | Sí | cadena de caracteres | Un parámetro que espera una lista separada por comas de las SKUs de destino de la campaña, por ejemplo, sku1, sku2, etc. |
| campaign\_name | No | string | El nombre de la campaña. |

</Accordion>

Para más información sobre cómo crear archivos fuente y subirlos a tu servicio en la nube, consulta la sección [Crear y conectar fuentes de datos personalizadas](#crear-y-conectar-fuentes-de-datos-personalizadas) de este documento.

## Flujo de ingestión de trabajos de atribución

Cada trabajo de atribución se dedica a un solo día y se ejecuta una vez finalizado. Al principio de este proceso, la tarea ingiere las conversiones, las interacciones y los datos de mapeo de campaña relevantes del servicio en la nube o de los eventos in-app.

<div id="campaign-mapping-source-ingestion" />

<Accordion title="Introducción de fuentes de mapeo de campañas">

Antes de cada ejecución de atribución, DCP carga los registros de asignación de campaña de las fuentes personalizadas. Puedes elegir entre dos modos para cargar estos registros:

* **Estrategia del último día**: DCP toma los registros más recientes en función de la fecha de carga de los registros.

  Por ejemplo, si la fuente contiene registros con fechas de carga del 18 de enero, 17 de enero o 29 de diciembre, el sistema seleccionará los registros con la fecha del 18 de enero.
* **Estrategia diaria**: DCP sólo toma los registros cuya fecha de carga coincide con el día de la ejecución de la atribución. Por ejemplo, si la ejecución se produce a medianoche del 19 de enero, el sistema sólo seleccionará los registros de campaña con la fecha de carga del 19 de enero.

</Accordion>

<div id="conversion-source-ingestion" />

<Accordion title="Introducción de fuentes de conversión">

Al final de cada día, DCP ejecuta el trabajo de atribución de ese día **sólo si puede acceder a la carpeta dedicada a ese día y a los registros de conversión que contiene**. Sin embargo, puede cargar la carpeta de un día determinado más adelante. Por ejemplo, puede cargar la carpeta del 17 de enero el 22 de enero.

* Al final de cada día, DCP ejecuta el trabajo de atribución de ese día. El trabajo se ejecutará **sólo si DCP puede encontrar la carpeta para ese día**. El nombre de la carpeta es idéntico al nombre del día.
* La carpeta del día puede incluir registros de eventos que se remontan a 30 días desde el día de la carpeta. Por ejemplo, en la carpeta Ene 17, el trabajo procesa los registros del 18 de diciembre al 17 de enero.
* Si omites subir la carpeta de un día determinado, dispones de 30 días para subirla. Por ejemplo, si te saltaste subir la carpeta del 17 de enero, puedes subirla hasta el 17 de febrero. No obstante, recomendamos subirla lo más cerca posible de la fecha de la carpeta.
* Si DCP no encuentra la carpeta del día actual, continuará buscando la carpeta cada 10 minutos durante los 7 días siguientes.

</Accordion>

<div id="engagement-source-ingestion" />

<Accordion title="Introducción de fuentes de engagement">

Para cada registro de conversión, DCP busca los eventos de engagement que la desencadenaron.

* Los registros de engagement se incluyen en carpetas fechadas. Sin embargo, no tienes que cargar una carpeta de engagement para cada día. Por ejemplo, puedes cargar las carpetas Ene 13 y Ene 15 sin cargar la carpeta Ene 14. En este ejemplo, los registros de Ene 14 se tomarán de la carpeta Ene 15.
* **El trabajo de atribución para una carpeta de conversión determinada sólo se iniciará si existe una carpeta de engagement con la misma fecha que la carpeta de conversión o una fecha posterior.** Por ejemplo, el trabajo de atribución para la carpeta de **conversión** del 17 de enero sólo se iniciará si existe la carpeta de engagement Ene 17 o carpetas con fechas posteriores, como Ene 18.
* El trabajo de atribución recopila todos los eventos de engagement que caen dentro de la ventana de lookback del engagement.

</Accordion>

<div id="inapp-data-ingestion" />

<Accordion title="Introducción de datos in-app">

Los datos de conversión y engagement pueden proceder de eventos in-app, fuentes personalizadas o una combinación de ambas. DCP te permite elegir entre utilizar un único modo o mezclarlos, permitiendo que las conversiones procedan de eventos in-app mientras que los engagements se obtengan de archivos personalizados, o viceversa.

Al configurar eventos in-app para conversiones, engagements o ambos, debes especificar el ID de la aplicación y el nombre del evento de conversión o engagement. Al final del día, el trabajo de atribución selecciona todos los eventos con el nombre y el ID de aplicación especificados que tengan la misma fecha de evento que el día de conversión.

</Accordion>

## Crear y conectar fuentes de datos personalizadas

Para conectar datos a través de fuentes personalizadas, el cliente deberá seguir primero las instrucciones de los siguientes artículos de la base de conocimientos de DCP:

* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">Plataforma de colaboración de datos - Configura tus servicios en la nube</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections">Plataforma de colaboración de datos - Añadir conexiones</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboración de datos: crea y gestiona fuentes</Anchor>

<div data-zendesk-anchors="overview=nota h_01JJKFW5Z2D7Y1MM5A7YR0TY0T=nota prepare-inapp-events-for-conversions-and-engagements=preparar-eventos-in-app h_01JJKFW5Z22DG4CKFMXPGR3BW0=preparar-eventos-in-app h_01JJKFW5Z2NP9187GYHS0YEXED=nota-1 h_01JJKFW5Z2AX7SHHZ23P0KDQJY=prepare-conversion-inapp-events h_01JJKFW5Z2YD0B151VSR3TG6SP=prepare-engagement-inapp-events h_01JJKFW5Z3QES9BAZX7KNSPCM8=create-inapp-events prepare-custom-source-files-for-engagements-and-conversions=preparar-archivos-fuente-personalizados h_01JJKFW5Z3QX33NK3XP452AAFB=preparar-archivos-fuente-personalizados h_01JK3QFQCK30A7SSPWXSH3VP0D=the-conversion-source-scheme media-partners=partners-de-medios-seleccionados h_01K399C7NME67HQGJKRG1A5JB2=partners-de-medios-seleccionados background-colors=colores-de-fondo h_01K399DC8ZAEA86DD4W0181EM6=colores-de-fondo h_01JK3QFQCKD1TV5G4N0KP85AWS=the-engagement-source-scheme h_01JK3QFQCK6C16SCW8EYQNS47F=nota-2 prepare-campaign-mapping-source=preparar-la-fuente-de-mapeo-de-la-campa%C3%B1a h_01JJKFW5Z3QR107P3M111P4STG=preparar-la-fuente-de-mapeo-de-la-campa%C3%B1a h_01JJKFW5Z3ZSYET4HMWD7TWSD8=nota-3 h_01JJKFW5Z3Q6F3DP0EMTNQRD8R=the-campaign-mapping-scheme prepare-data-for-attribution-job-ingestion=flujo-de-ingesti%C3%B3n-de-trabajos-de-atribuci%C3%B3n h_01JJKFW5Z38W581F4CBW3T4CPZ=flujo-de-ingesti%C3%B3n-de-trabajos-de-atribuci%C3%B3n h_01JK5R1VPJ0WAF3WX4R1ECE0R7=campaign-mapping-source-ingestion h_01JK5R1VPJT41RF2EN8806ZY5C=conversion-source-ingestion h_01JK5R1VPJN8KTFTN21DA3619Y=engagement-source-ingestion h_01JK5R1VPJV6F5Y5JB3Q45R89B=inapp-data-ingestion create-and-connect-custom-data-sources=crear-y-conectar-fuentes-de-datos-personalizadas h_01JJKFW5Z3NKB0MB7GN2FC87H5=crear-y-conectar-fuentes-de-datos-personalizadas" />
