---
title: Asignación de eventos in-app de anuncios de Meta
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-09-12T00:28:07Z'
  id: 4410480904081
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/4410480904081
---
> **De un vistazo:** Envía los eventos in-app enriquecidos de tu app desde AppsFlyer a Anuncios de Meta.

## Asignación de eventos in-app de Meta

Los anunciantes asignan sus eventos in-app, SDK o Servidores a servidores, a eventos predefinidos de Meta. Los anunciantes también pueden enviar postbacks a Meta sobre cada <Anchor target="_blank" href="/marketers/es/docs/measure-sessions">inicio de la aplicación</Anchor> o cada evento conocido de <Anchor target="_blank" href="/marketers/es/docs/measure-uninstalls#mapeo-del-evento-de-desinstalación">desinstalación de la aplicación</Anchor>.

Esto permite a los anunciantes utilizar las capacidades de optimización avanzada de Meta, así como crear segmentos de audiencia personalizados y similares.

### Asignación de eventos predefinidos

Anuncios de Meta ofrece una <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">amplia gama de eventos</Anchor> que ya están predefinidos y se pueden asignar.

Encuentra <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">aquí</Anchor> la lista de **eventos in-app enriquecidos** que se pueden enviar a Meta con parámetros adicionales que proporcionan **información adicional sobre la calidad de los eventos**.

Aprender más sobre la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#inapp-event-mapping">asignación de eventos de Meta</Anchor>.

[![In-app_event_postbacks_es-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

Ten en cuenta que no hay un evento predefinido para enviar desinstalaciones a Anuncios de Meta. Para enviar desinstalaciones, usa un [evento personalizado](/docs/meta-ads-in-app-event-mapping#asignación-de-eventos-in-app-personalizados).

A continuación se muestra la lista de otros eventos predefinidos de Meta que no tienen parámetros adicionales:

| Identificador de evento de Meta | Descripción | Nombre recomendado del SDK de AppsFlyer |
| --- | --- | --- |
| Donate | La donación de fondos a tu organización o causa. | af\_donate |
| Schedule | La reserva de una cita para visitar una de tus ubicaciones. | af\_schedule |
| SubmitApplication | La presentación de una solicitud para un producto, servicio o programa que ofrezcas, como una tarjeta de crédito, programa educativo o trabajo. | af\_submit\_application |
| FindLocation | Cuando una persona encuentra una de tus ubicaciones a través de la web o la aplicación, con la intención de visitarla. Por ejemplo, buscar un producto y encontrarlo en una de tus tiendas locales. | af\_find\_location |
| Contacto | Un teléfono o SMS, correo electrónico, chat u otro tipo de contacto entre un cliente y tu negocio. | af\_contact |
| CustomizeProduct | La personalización de productos a través de una herramienta de configuración u otra aplicación de tu empresa. | af\_customize\_product |
| `Adimpression`—para Android  <br />`Fb_mobile_purchase`—para iOS | Optimiza los ingresos por anuncios en la plataforma de anuncios de Meta. [Consulta los detalles a continuación](#mapeo-de-datos-de-ingresos-por-anuncios-para-la-optimización-de-campañas). | af\_ad\_revenue |

### Mapeo de datos de ingresos por anuncios para la optimización de campañas

Meta ads pueden optimizar tus campañas en función de tus datos de ingresos por anuncios. Esto se hace asignando el evento af\_ad\_revenue al siguiente evento de Meta ads:

<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th><strong>Nombre del evento en AppsFlyer</strong></th><th><strong>Destino de engagement</strong> </th><th><strong>Asignado a un evento de partner</strong></th><th><strong>Optimización de Meta ads basada en:</strong></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>Android</td><td>Adimpression</td><td>Ingresos por anuncios específicos</td></tr><tr><td>apps de iOS,</td><td>fb_mobile_purchase</td><td>Compras in-app</td></tr></tbody></table>

#### Limitaciones de disponibilidad

* Actualmente, la optimización mediante el evento **Adimpression** solo está disponible para:
  * Aplicaciones de Android. Las apps de iOS pueden seguir enviando datos de ingresos por anuncios mediante el evento *fb\_mobile\_purchase*.
  * Cuentas seleccionadas de Meta ads, según los criterios de Meta. Cuando esté en gris, [los criterios de elegibilidad pueden no cumplirse](https://www.facebook.com/business/help/571188993373447?id=561906377587030).
* El evento *af\_ad\_revenue* solo está disponible para planes con una <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data">suscripción avanzada de ROI360</Anchor>. Además, necesitas el <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipo de integración de ingresos por anuncios a nivel de impresión mediante SDK</Anchor>.
  * Los planes que no son ROI360 pueden enviar datos de ingresos publicitarios utilizando otros nombres de eventos.

### Asignación de eventos in-app personalizados

AppsFlyer te permite asignar cualquier evento in-app personalizado para enviarlo a Meta, utilizando la opción de Identificador de eventos PERSONALIZADO de Meta.

El nombre del evento y el valor del evento (incluidos los parámetros del mismo) configurados en el SDK se reenvían a Meta, tal como están, y se muestran bajo su nombre de evento original del SDK de AppsFlyer, no como "custom".

Ten en cuenta que puedes <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">utilizar estos eventos para optimizar tus campañas</Anchor>.

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### Asignación automática de parámetros con evento PERSONALIZADO

A través de la integración profunda de AppsFlyer con Meta, muchos de los parámetros de eventos del SDK estándar de AppsFlyer se asignan automáticamente a los parámetros predefinidos de Meta. Por ejemplo, el parámetro **af\_revenue** se convierte en el parámetro **\_valueToSum** en Meta, lo que te permite enviar un ingreso por evento que se puede medir y optimizar en Meta.

> 📘 **Nota**
>
> La asignación automática de parámetros puede diferir entre eventos PERSONALIZADOS y predefinidos.
>
> Con respecto a los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">eventos predefinidos</Anchor>, **af\_price** se asigna a **\_valueToSum** en algunos casos (por ejemplo, `fb_mobile_add_to_cart`). En otros casos, **af\_revenue** se asigna a **\_valueToSum** (por ejemplo, en `fb_mobile_purchase`).
>
> Con respecto a los eventos asignados a PERSONALIZADOS, **af\_price** siempre se asigna a **fb\_price** y **af\_revenue**, a **\_valueToSum**.

La siguiente tabla detalla todos los parámetros de eventos de AppsFlyer, que, cuando se asignan mediante el evento PERSONALIZADO a Meta, se asignan automáticamente a los parámetros de Meta.

| Parámetro de AppsFlyer | Parámetro de Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | {"fb_destination_"}  <br />airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

#### Mapeo automático de eventos predefinidos al parámetro `_valueToSum`

En los eventos predefinidos, el parámetro de Meta `_valueToSum` se asigna al parámetro `af_price` o al parámetro `af_revenue`.

La siguiente tabla detalla esta asignación para todos los eventos predefinidos de Meta con el parámetro `_valueToSum`:

| **Punto (.)** | **\_valueToSum asignado a** |
| --- | --- |
| fb\_mobile\_level\_achieved | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_price |
| fb\_mobile\_add\_to\_wishlist | af\_price |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_mobile\_initiated\_checkout | af\_price |
| fb\_mobile\_purchase | af\_revenue |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_revenue |
| fb\_mobile\_spent\_credits | af\_price |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_price |
| Comenzar prueba | af\_price |
| Suscribirse | af\_revenue |

### Envía eventos in-app complejos a Meta ads

A partir de septiembre de 2026, te recomendamos usar el nuevo objeto `af_order_info` para enviar eventos in-app complejos, es decir, eventos con varios artículos, a Meta Ads. Este objeto permite a los anunciantes compartir eventos in-app complejos con varias redes compatibles. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/item-level-order-data-for-ad-networks-af-order-info">Datos de pedidos a nivel de artículo para redes publicitarias (af\_order\_info)</Anchor>.

Cuando usas `af_order_info`, AppsFlyer envía la información de los artículos a Meta en el campo de evento `fb_contents`, que admite SKU, cantidad e ingresos por artículo.

Como alternativa, también puedes seguir usando una matriz estructurada `af_content`. Cada objeto de la matriz debe incluir `id` y `quantity` para garantizar un procesamiento correcto del postback.

`af_content_list` es opcional. Cuando no está presente, Meta recurre al campo `fb_content` (mapeado desde `af_content`) para identificar los ID de producto. Siempre que el JSON de `af_content` incluya un campo `id` en cada objeto, Meta puede analizarlo y extraer de él los ID de contenido.

Si incluyes `af_content_list`, no incluyas también `af_content_id` en el mismo evento. Ambos parámetros se asignan a `fb_content_id`, y solo debe rellenarse uno para evitar conflictos.

> 📘 **Advertencia**
>
> `fb_content_id` es importante para casos de uso a nivel de producto, como asociar eventos con artículos del catálogo para Advantage+ Catalog Ads y Dynamic Ads, los informes de rendimiento a nivel de producto y las señales de optimización basadas en productos. Para la optimización general de conversiones basada en el recuento y el valor de los eventos, las campañas funcionan sin él.

> 📄 **Ejemplo de formato unificado compatible con Meta y TikTok**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
> }
> ```

Este formato funciona tanto para Meta como para TikTok. TikTok también lee los valores de `id` del campo `af_content`, por lo que una sola carga útil es suficiente cuando envías un postback a ambas redes.

> 🚧 **Dos puntos (:)**
>
> Si el parámetro `af_content` supera los 1.000 caracteres, AppsFlyer puede enviar el evento a Meta sin el parámetro `fb_content`. Si `af_content_list` tampoco está presente en ese caso, Meta no recibe datos de identificación del producto. Mantén `af_content` por debajo de los 1.000 caracteres en los eventos que incluyan muchos artículos.

Para obtener más información sobre cómo estructurar eventos in-app complejos, consulta el artículo <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">Eventos in-app: descripción general</Anchor>.

## Limitaciones de eventos y parámetros

Los siguientes límites se aplican a los [eventos que envías a Anuncios de Meta](https://developers.facebook.com/docs/app-events/faq#limits):

* Los siguientes caracteres no están permitidos:
  * Dos puntos (:)
  * Punto (.)
  * Conjuntos de caracteres no latinos (inglés): a partir del 12 de enero de 2020, Meta rechaza los caracteres chinos. AppsFlyer no ha probado otros conjuntos de caracteres y debes usarlos solo después de verificar con Meta si estos son compatibles en los postbacks.
* Los nombres de eventos distinguen entre mayúsculas y minúsculas. Para evitar discrepancias, asegúrate de usar las mayúsculas y minúsculas correctas en los nombres de eventos para todas las fuentes de medios y versiones de aplicaciones.
* Número máximo de parámetros: 25.
* Longitud de los nombres de evento y parámetros: 2–40.
* Longitud máxima de los parámetros: 100 caracteres.
* Longitud máxima del parámetro af\_content: 1000 caracteres.
* Caracteres permitidos: caracteres alfanuméricos, guiones bajos, guiones o espacios. No utilices caracteres no latinos (inglés). El uso de letras no latinas causa resultados incoherentes.

Consideraciones sobre la nomenclatura de eventos in-app:

* Los nombres de eventos de AppsFlyer pueden coincidir con los nombres de eventos de Meta (por ejemplo, fb\_price). Sin embargo, no podrán enviarse como eventos PERSONALIZADOS a Meta.  
  **Por las dudas, evita poner a los eventos el mismo nombre que el de los eventos de Meta.**
* Para realizar una asignación de postbacks de eventos in-app con Meta, obtén los datos de los eventos de todas las fuentes, incluidas las orgánicas.

> 🚧 **¡Importante!**
>
> A excepción de los parámetros anteriores, AppsFlyer envía los datos de eventos PERSONALIZADOS **tal como están** a Meta. Es responsabilidad del propietario de la aplicación verificar que los datos del evento cumplan con los requisitos de Meta, utilizando parámetros válidos de Meta (ver la tabla anterior). De lo contrario, estos parámetros no se envían a Meta.

<div data-zendesk-anchors="facebook-iae-mapping=asignaci%C3%B3n-de-eventos-in-app-de-meta h_01J1WCP44CHN0Q73P6DN7H8FKG=asignaci%C3%B3n-de-eventos-in-app-de-meta predefined-event-mapping=asignaci%C3%B3n-de-eventos-predefinidos h_01J1WCP44D18WMXCMHJ0FNF6Y0=asignaci%C3%B3n-de-eventos-predefinidos mapping-ad-revenue-data-for-campaign-optimization=mapeo-de-datos-de-ingresos-por-anuncios-para-la-optimizaci%C3%B3n-de-campa%C3%B1as 01JAPZ6M11HSCE9QNN5NSD61FK=mapeo-de-datos-de-ingresos-por-anuncios-para-la-optimizaci%C3%B3n-de-campa%C3%B1as availability-limitations=limitaciones-de-disponibilidad 01JAQ1ECZVR8SZ81KE6CDD08A2=limitaciones-de-disponibilidad custom-inapp-events-mapping=asignaci%C3%B3n-de-eventos-in-app-personalizados h_01J1WCP44DK14AC5ZG4KTFFFSC=asignaci%C3%B3n-de-eventos-in-app-personalizados automatic-parameter-mapping-with-the-custom-event=asignaci%C3%B3n-autom%C3%A1tica-de-par%C3%A1metros-con-evento-personalizado h_01J1WCP44D645TS6JFGM2BDGM9=asignaci%C3%B3n-autom%C3%A1tica-de-par%C3%A1metros-con-evento-personalizado h_01J1WCP44DSZ7G3603W5EBWZEW=nota value-to-sum=mapeo-autom%C3%A1tico-de-eventos-predefinidos-al-par%C3%A1metro-_valuetosum 01JATBG1SZRRZ0PCANKQ6S8CX4=mapeo-autom%C3%A1tico-de-eventos-predefinidos-al-par%C3%A1metro-_valuetosum send-complex-in-app-events-to-meta-ads=env%C3%ADa-eventos-in-app-complejos-a-meta-ads h_01K1QR0NWMT1WCFWXF2GK9YZYF=env%C3%ADa-eventos-in-app-complejos-a-meta-ads h_01KSMX6DZHA1HNQ2WGECZPEQGJ=advertencia h_01KSMX6DZHF0P97RTJHS065KB1=ejemplo-de-formato-unificado-compatible-con-meta-y-tiktok h_01KSMX6DZHWXYRJP5QK5BB730P=dos-puntos- event-and-parameter-limitations=limitaciones-de-eventos-y-par%C3%A1metros h_01J1WCP44DF2QMV10VXF8NQZ7W=limitaciones-de-eventos-y-par%C3%A1metros h_01J1WCP44D9SNEYZG59KNM822K=importante" />
