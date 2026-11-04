---
title: Integración con Google Analytics (GA4)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-09-29T00:05:48Z'
  id: 25707682812561
  locale: es
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/es/articles/25707682812561
---
> **At a glance:** La integración de AppsFlyer con Google Analytics (GA4) permite a los anunciantes enviar datos de atribución y eventos seleccionados in-app desde AppsFlyer a GA4. Esta integración funciona con aplicaciones de iOS y Android que ya tienen implementado el [SDK de Google Analytics para Firebase](https://firebase.google.com/docs/analytics).

> 🚧 **Important**
>
> **Importante:**
>
> Esta integración funciona con aplicaciones de iOS y Android que ya tienen implementado el [SDK de Google Analytics para Firebase](https://firebase.google.com/docs/analytics). Para que la integración tenga éxito, el SDK de AppsFlyer debe recopilar el valor `app_instance_id` del SDK de Firebase. Consulta las instrucciones sobre [cómo recuperar el ID de instancia de la aplicación del SDK de Firebase](#5-retrieve-app-instance-id-in-appsflyer-sdk).

<div id="how-does-it-work" />

## ¿Cómo funciona?

* Cuando ocurre una nueva instalación, AppsFlyer envía los detalles del punto de contacto: fuente de medios, nombre de la campaña e ID de la campaña a GA4. También envía el `app_instance_id` del SDK de Firebase para asegurar que el punto de contacto se registre en GA4 para ese usuario.
* Cuando ocurre un evento in-app, GA4 atribuirá el evento al último punto de contacto.

<div id="set-up-google-analytics-ga4-integration" />

## Configurar la integración de Google Analytics (GA4)

Sigue las instrucciones a continuación para configurar la integración con Google Analytics (GA4).

<Accordion title="1. Selecciona Google Analytics (GA4) en el Partner Marketplace">

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">ponerte en contacto con el partner</Anchor> y abrir una cuenta con él.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca Google Analytics (GA4) y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   Nota: El selector **debe permanecer activado (activo) mientras trabajes con Google Analytics (GA4)**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

La configuración de Google Analytics solo incluye la pestaña **Integración**.

Para ver una descripción detallada del encabezado de la ventana de configuración del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

</Accordion>

<Accordion title="2. Configurar la integración de GA4 en AppsFlyer">

Configura los siguientes ajustes:

1. En la pestaña **Integración**, selecciona la aplicación para la integración y activa **Activar partner**.

   **Nota:** El selector debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.

   Para obtener más detalles sobre la activación del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
2. En **ID de la aplicación de Firebase,** introduce el identificador de la aplicación de Firebase. Para saber cómo localizar el ID de la aplicación de Firebase, consulta <Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">la documentación de Firebase</Anchor>.
3. En **API Secret,** introduce la API Secret que se usa para autenticar los postbacks a Google Analytics. Una API Secret se genera a través de la interfaz de usuario de Google Analytics. Para ver, editar o crear un secreto, sigue las instrucciones de la <Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">documentación de Google</Anchor>. **Cuando se te indique seleccionar un flujo de datos web, elige un flujo de datos de Android o iOS en su lugar.**
4. Activa **Customer User ID** para enviar el ID de usuario del cliente (CUID) en lugar del ID de publicidad (IDFA).
5. En la sección **Postbacks predeterminados**, en **para usuarios de**, selecciona **Todas las fuentes de medios, incluido orgánico**.

> 📘 **Note**
>
> **Nota:**
>
> El postback de instalación incluye solo los detalles del punto de contacto (fuente de medios, nombre de campaña e ID de campaña).

</Accordion>

<Accordion title="3. Configurar postbacks predeterminados">

AppsFlyer puede enviar postbacks automáticos a GA4 después de las instalaciones de usuarios, incluidas tanto las instalaciones como los re-engagements (incluidas las reatribuciones). Los re-engagements se producen cuando un usuario que ya tiene la aplicación instalada la abre después de hacer clic en un enlace de campaña. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor>.

</Accordion>

<Accordion title="4. Configurar postbacks de eventos in-app">

En la pestaña **Integración**, mapea los eventos in-app de AppsFlyer a los eventos de Google Analytics (GA4), enviados a través de postbacks.

> 📘 **Note**
>
> **Nota:**
>
> * Los postbacks para eventos in-app móviles enviados a través de S2S no son compatibles.
> * GA4 no deduplica eventos enviados desde el SDK de Firebase y AppsFlyer. Recomendamos configurar postbacks de eventos in-app solo para eventos que no se envían ya a GA4 a través del SDK de Firebase.

1. Activa los **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para añadir un evento del SDK a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre del parámetro | Description |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como se recibe desde el SDK de AppsFlyer integrado en tu app.<br /><br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer** y, a continuación, haz clic en **Crear personalizado**.</li></ul>Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación personalizada de eventos.</Anchor> |
| **Asignado al evento de socio** | El nombre o ID único de cada evento, definido por el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** Obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | Seleccione la opción de envío para el evento:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner, así como eventos orgánicos.</li></ul> |
| **incluye** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí, sin ningún valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros, **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** (<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />) para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
4. Haz clic en **Guardar integración**.
5. Enviar el mapeo de postback de eventos

</Accordion>

<Accordion title="5. Envía a tu desarrollador el mapeo de eventos de postback">

Después de haber configurado el mapeo de eventos in-app, envía a tu desarrollador una tabla donde cada evento mapeado corresponda a una fila con las siguientes columnas:

* **Evento de AF:** Nombre del evento de AppsFlyer.
* **Asignado al evento de Google:** Nombre del evento en Google Analytics.

> 🚧 **Important**
>
> **Importante:**
>
> No utilices ninguno de los [eventos reservados de Google](#nombres-reservados-de-eventos-de-google) como nombres para eventos personalizados de Google Analytics.

* **Parámetros del evento de AF (OBLIGATORIOS):** Parámetros de evento de AppsFlyer predefinidos que deben incluirse en el postback de evento enviado a Google Analytics.

> 🚧 **Important**
>
> **Importante:**
>
> Es obligatorio incluir todos los parámetros de evento AF predefinidos dentro de la definición del evento exactamente como se enumeran en la tabla; no hacerlo resultará en que Google Analytics rechace el postback.

<div id="the-event-mapping-table" />

#### La tabla de mapeo de eventos

La siguiente tabla incluye todos los eventos de Google Analytics y sus parámetros predefinidos de AppsFlyer. Envía a tu desarrollador una tabla que contenga solo los eventos que has mapeado.

| Nombre recomendado por AF (Opcional) | El nombre del evento de Google Ads | Parámetros de evento predefinidos de AF (OBLIGATORIO) |
| --- | --- | --- |
| af\_add\_payment\_info | [add\_payment\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [añadir\_al\_carrito](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | campaign id, campaign name |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_level\_achieved | [level\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [Iniciar sesión](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_compra | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [share](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_search\_results](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

<div id="reserved-google-event-names" />

#### Nombres reservados de eventos de Google

Los siguientes nombres de eventos están reservados y no se pueden usar como nombres de eventos personalizados:

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `excepción_de_la_aplicación`
* `instalación_de_la_aplicación`
* `eliminación_de_la_aplicación`
* `reembolso_de_la_tienda_de_aplicaciones`
* `app_update`
* `actualización_de_la_aplicación`
* `apertura_de_la_aplicación_mediante_enlace_dinámico`
* `actualización_de_la_aplicación_mediante_enlace_dinámico`
* `primera_apertura_mediante_enlace_dinámico`
* `error`
* `campaña_de_firebase`
* `acción_del_mensaje_in-app_de_firebase`
* `cierre_del_mensaje_in-app_de_firebase`
* `impresión_del_mensaje_in-app_de_firebase`
* `primera_apertura`
* `primera_visita`
* `in_app_purchase`
* `descarte_de_notificación`
* `notificación_en_primer_plano`
* `notification_open`
* `recepción_de_notificación`
* `envío_de_notificación`
* `actualización_del_sistema_operativo`
* `inicio_de_sesión`
* `engagement_del_usuario`

</Accordion>

<Accordion title="6. Recuperar el ID de instancia de la aplicación en el SDK de AppsFlyer">

El `app_instance_id` identifica de forma única una instalación de la app de Firebase, y el `ga_session_id` identifica de forma única una sesión de la app de Firebase. Recupera estos valores desde el SDK de Firebase y, después, envíalos a GA4 con la API `setAdditionalData`.

Deja que tu desarrollador implemente el código para:

1. Recopila de Firebase los campos `app_instance_id` y `ga_session_id`.
2. Llama a `setAdditionalData` antes del primer inicio para incluir el ID de instancia de la aplicación y `ga_session_id` en instalaciones, sesiones y eventos in-app.

> 🚧 **Important**
>
> **Importante:**
>
> `setAdditionalData` (Android / Unity / React Native) y `customData` (iOS) aceptan un **mapeo de pares clave-valor**. Envía tanto `app_instance_id` como `ga_session_id` **juntos en el mismo mapeo**, para que se incluyan ambos valores. Si los envías en llamadas **independientes** a `setAdditionalData`, la última sobrescribirá la anterior.

<Tabs>
<Tab title="Android nativo">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS nativo">

**iOS nativo**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React Native">

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="7. Recuperar el ID de sesión de GA4 en el SDK de AppsFlyer">

El `ga_session_id` identifica de forma única una sesión de una aplicación de Firebase. Este valor debe recuperarse del SDK de Firebase y enviarse a GA4 mediante la API `setAdditionalData`.

Deja que tu desarrollador implemente el código para:

1. Recoge el campo `ga_session_id` de Firebase.
2. Llama a `setAdditionalData` antes del primer inicio para incluir el ID de sesión (y `app_instance_id`, si se usa).
3. Usa la clave `ga_session_id` al llamar a la API.

> 🚧 **Important**
>
> **Importante:**
>
> `setAdditionalData` (Android / Unity / React Native) y `customData` (iOS) aceptan un **mapeo de pares clave-valor**. Si tu aplicación envía tanto `app_instance_id` como `ga_session_id` (consulta el [paso 5](#5-retrieve-app-instance-id-in-appsflyer-sdk)), **envíalos juntos en el mismo mapeo** para que se incluyan ambos valores. Si los envías en llamadas **independientes** a `setAdditionalData`, la última sobrescribirá la anterior.

<Tabs>
<Tab title="Android nativo">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS nativo">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

Referencia de API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="8. Valida la integración de GA4">

Asegúrate de que los eventos en los postbacks que envías a GA4 estén registrados y leídos por Google Analytics. Hay dos métodos que los anunciantes pueden usar para ver sus datos:

* Usando [Exploraciones de GA4](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article), puedes explorar los datos de eventos en bruto con todos los parámetros asociados. **Requisito previo:** [La exportación de BigQuery](https://support.google.com/analytics/answer/9823238) debe estar configurada en tu propiedad)
* **El reporte de eventos** permite a los anunciantes ver sus eventos de postback. El reporte se puede encontrar en una o más colecciones de reportes.  
  Por ejemplo, los reportes de eventos se pueden encontrar en las colecciones [Ciclo de vida](https://support.google.com/analytics/answer/12924233?hl=en) o [Reportes de juegos](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC), en **engagement** > **Eventos**.   
  Para más información sobre el reporte de eventos, consulta [la documentación de Google](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC).

  ![Reporte de eventos de GA4](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **El reporte de adquisición de tráfico** te ayuda a entender de dónde provienen los visitantes de tu sitio web y aplicación.

  En la [colección Ciclo de vida](https://support.google.com/analytics/answer/12924233?hl=en), ve a **Adquisición** > **Adquisición de tráfico**).

  Para más información sobre el reporte de adquisición de tráfico, consulta [la documentación de Google](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report).

  ![Reporte de adquisición de tráfico de GA4](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)

</Accordion>

<div data-zendesk-anchors="set-up-google-analytics-ga4-integration=c%C3%B3mo-funciona h_01HZXY8R12MQWKNHX2BXA68MR3=c%C3%B3mo-funciona h_01J35AP3FF599P0XA8VPWTS5R9=configurar-la-integraci%C3%B3n-de-google-analytics-ga4 the-event-mapping-table=la-tabla-de-mapeo-de-eventos h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=la-tabla-de-mapeo-de-eventos reserved-google-event-names=nombres-reservados-de-eventos-de-google h_01HZQ4ABBN6ZEB7RJQMFS0AB73=nombres-reservados-de-eventos-de-google" />
