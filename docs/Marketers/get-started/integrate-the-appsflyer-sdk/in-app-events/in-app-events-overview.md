---
title: 'Eventos in-app: general'
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-09T00:06:26Z'
  id: 115005544169
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/115005544169
---
> **At a glance:** Registra eventos in-app posteriores a la instalación (como inicio de sesión, registro o compras dentro de la aplicación) atribuidos a fuentes de medios y campañas.

<div id="why-record-in-app-events" />

## ¿Por qué registrar eventos in-app?

Los eventos in-app ofrecen información sobre lo que ocurre en tu aplicación y son la herramienta ideal para determinar el valor de los usuarios y la **calidad del tráfico proveniente de diferentes fuentes de medios**. Registrar eventos in-app te ayuda a medir indicadores clave de rendimiento (KPI), como el ROI (Return on Investment) y el LTV (Lifetime Value).

Cuando los usuarios se registran, completan tutoriales, añaden artículos al carrito de compras o realizan compras, los datos de eventos in-app pueden registrar estos eventos con detalles específicos. La implementación de eventos in-app es obligatoria para todos los análisis posteriores a la instalación.

<div id="about-in-app-events" />

## Sobre los eventos in-app

Un evento in-app comprende un nombre de evento y puede incluir parámetros de evento. Cuando se agregan parámetros a un evento in-app, se le denomina evento in-app. Los parámetros de evento te proporcionan más contexto e información sobre el evento en cuestión. Por ejemplo, saber que un usuario ha hecho una reserva es útil, pero los parámetros del evento pueden ofrecerte detalles como el tipo de compra, el destino y los ingresos.

![viaje.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

<div id="tip" />

> 👍 **Consejo**
>
> ¿Quieres saber más sobre los eventos in-app? Consulta este breve e informativo <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">curso en el portal de aprendizaje de AppsFlyer</Anchor>.

<div id="predefined-and-custom-events" />

### Eventos predefinidos y personalizados

Para enviar eventos in-app, es necesario que el desarrollador implemente el código correspondiente en la aplicación. Los nombres de eventos y parámetros de eventos se clasifican de la siguiente manera:

* **Predefinido**: Estos son nombres y parámetros de eventos que se utilizan comúnmente entre diversas aplicaciones. Recomendamos encarecidamente utilizar <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#nombres-de-eventos-predefinidos">nombres de eventos predefinidos</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#parámetros-de-evento-predefinidos">parámetros de eventos</Anchor> siempre que sea posible por los siguientes motivos:
  * La nomenclatura predefinida permite una asignación fluida de eventos a partners.
  * Si AppsFlyer decide cambiar el nombre de cualquier evento o parámetro de evento, la implementación seguirá siendo compatible con versiones anteriores.
* **Personalizado:** Estos son los nombres de eventos y parámetros que defines para escenarios específicos de usuario que ocurren en tu aplicación. Puedes utilizar cualquier nombre de evento o de parámetro personalizado, pero recuerda que estos eventos requieren mantenimiento por parte de tu desarrollador. Consulta [Consejos](/docs/in-app-events-overview#tips) y [Limitaciones](/docs/in-app-events-overview#limitations).

<div id="revenue-in-in-app-events" />

## Ingresos en eventos in-app

La información en las siguientes secciones explica cómo puedes enviar eventos de ingresos a AppsFlyer y mapear los parámetros que incluyen los eventos. Sin embargo, es importante señalar que con una suscripción a ROI360, obtienes los datos de costos e ingresos más precisos y actualizados disponibles (incluidos los datos de ingresos de compras in-app, suscripciones y anuncios). <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data">Saber más sobre ROI360</Anchor>

<Accordion title="Ingresos por evento">

`af_revenue` es el parámetro predeterminado para reportar ingresos. Los ingresos enviados en `af_revenue` alimentan todas las métricas de ingresos en los productos de AppsFlyer (dashboards, LTV, cohorte, ROAS, ROI) y se incluyen en postbacks a partners. Utilízalo siempre con eventos in-app que representen la generación de ingresos reales en tu lógica comercial.

Si también quieres reportar ingresos aplicando tu propia lógica, por ejemplo, después de las comisiones de la tienda de aplicaciones y las deducciones fiscales, también puedes enviar `af_net_revenue`. Es un complemento de `af_revenue`, no un sustituto. Consulta [Ingresos netos](#net-revenue) más abajo.

* <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#record-revenue">Registro de ingresos en el SDK</Anchor>
* Registro de ingresos en Unity

También puedes registrar ingresos negativos cuando un usuario cancela una compra o cuando emites un reembolso. Para registrar ingresos negativos, solo tienes que añadir el signo menos (-) al valor de ingresos que pasas a `af_revenue`

El valor de ingresos debe contener solo números (y un punto decimal si es necesario):

* **No** incluyas ningún otro carácter o formato al valor de ingresos de ninguna otra manera. Esto significa sin comas, signos de moneda (por ejemplo, $), caracteres especiales o texto.
* AppsFlyer proporciona el valor de ingresos con **precisión de hasta cinco decimales**.
* El intervalo de este valor debe ser de -1.000.000 a 1.000.000 en dólares o en su equivalente en la moneda original. Los valores fuera de este rango se incluyen en los reportes de raw data, pero no en los reportes agregados.
* Ejemplo: 1234,56
* Cuando los ingresos se envían como una cadena, el valor dentro de las comillas debe ser válido. Por ejemplo: "1234,56".

<div id="note" />

> 📘 **Nota:**
>
> AppsFlyer muestra los ingresos exactos tal como se envían desde el SDK. No se incluye ningún cálculo de IVA ni comisiones de la tienda de aplicaciones, etc., a menos que estos hayan sido añadidos por el desarrollador en el SDK antes de enviarlo a AppsFlyer. Si quieres reportar los ingresos después de esas deducciones, envíalos además en `af_net_revenue` (consulta [Ingresos netos](#net-revenue)).

`af_currency` representa la divisa utilizada en `af_revenue` (o en `af_price`). Si falta `af_currency` en los parámetros del evento, AppsFlyer lo envía con el valor predeterminado "USD".

Puedes usar `af_price` como un parámetro monetario que no se cuenta como ingresos (por ejemplo, en un evento de «Agregar al carrito»). Este parámetro se refiere al precio de un artículo individual. El monto total de todas las compras aparece en el parámetro `af_revenue`.

</Accordion>

<Accordion title="Ejemplo">

El parámetro `af_net_revenue` ofrece una forma opcional y adicional de reportar ingresos cuando quieres aplicar tu propia lógica al importe de ingresos; por ejemplo, ingresos después de las comisiones de la tienda de aplicaciones, deducciones fiscales, margen bruto o comisiones de servicio.

`af_net_revenue` **no sustituye a** `af_revenue`. Sigue enviando `af_revenue` como siempre y añade `af_net_revenue` junto con él cuando quieras reportar neto.

* La divisa sigue `af_currency` (USD de forma predeterminada), igual que `af_revenue`.
* Como no hay ninguna constante del SDK predefinida para `af_net_revenue`, debes enviarlo como un parámetro personalizado con la clave `af_net_revenue`.
* Los ingresos netos impulsan las métricas Net (ingresos netos, ROI neto, ROAS neto, ARPU neto y beneficio neto) en <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#metrics">Mis Dashboards</Anchor>.

<div id="note-1" />

> 📘 **Nota:**
>
> Si usas <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue">ROI360 store revenue</Anchor>, `af_net_revenue` se completa automáticamente para los eventos de compras in-app y suscripciones, por lo que no necesitas enviar `af_net_revenue` para esos eventos. Los ingresos netos equivalen a los ingresos brutos menos las comisiones de la tienda de aplicaciones y los impuestos.

</Accordion>

<Accordion title="Moneda de ingresos">

Es importante entender cómo AppsFlyer maneja la configuración de moneda y la conversión de monedas.

AppsFlyer gestiona la diferencia entre la moneda configurada en la aplicación y la moneda de los eventos in-app utilizando la conversión de moneda.

![flujo_de_normalización_de_ingresos.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

El diagrama anterior explica el siguiente proceso:

1. Se envían eventos dentro de la aplicación: moneda diferente para cada evento
2. AppsFlyer normaliza todas las monedas a USD
3. AppsFlyer procesa los datos de ingresos
4. Los datos de ingresos en el dashboard se muestran según la configuración de la moneda de la aplicación
5. AppsFlyer completa los datos de ingresos en los reportes de raw data en ambas moneda de evento y configuración de la aplicación.

AppsFlyer utiliza <Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor> para la conversión de moneda. El tipo de cambio se actualiza cada hora. Cada vez que AppsFlyer realiza una conversión de moneda, utiliza el tipo de cambio de la última actualización.

<div id="currency-conversion" />

#### Conversión de moneda

<span id="h_01HDBZW9XERK3VN1GS8GHM911W"></span>**Ejemplo**

En la configuración de tu aplicación, estableces la moneda en GBP. Un usuario de Francia compra un producto utilizando tu aplicación. El precio está en EUR (€). El evento in-app que envías a AppsFlyer se ve así:

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE,200);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType. PURCHASE , eventValue);
```

En este caso, AppsFlyer convierte los ingresos de EUR a USD y luego a GBP. Supongamos que el tipo de cambio es €1 = $1,13. Por lo tanto, €200 se convierten en $226,85. Luego, AppsFlyer convierte de USD a GBP. Supongamos que el tipo de cambio es $1 = £0,78. Entonces $226,85 se convierten en £176,92.

<div id="currency-display" />

#### Visualización de la moneda

<Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-currency">La moneda se establece en la configuración de la aplicación</Anchor>. La moneda que establezcas en la configuración de la aplicación será la moneda que aparecerá en el dashboard. No importa en qué moneda envíes eventos in-app, los ingresos en el dashboard siempre aparecen en la moneda que configures en los ajustes de la aplicación.

<span id="h_01HDBZW9XEQNG1RDH7A8H002ZD"></span>**Ejemplo**

Supongamos que envías eventos in-app con monedas diferentes a la establecida en los ajustes de la aplicación, o sin ninguna moneda en absoluto. En este ejemplo, la moneda en los ajustes de la aplicación está en **GBP**.

Envías tres eventos in-app a AppsFlyer.

1. El Evento A tiene ingresos de **234** y **GBP** como moneda.
2. El Evento B tiene ingresos de **171** y **EUR** como moneda.
3. El Evento C tiene ingresos de **171** pero **ninguna moneda especificada**.

<div id="revenue-data-in-the-dashboard" />

#### Datos de ingresos en el dashboard

Los ingresos que aparecen en el dashboard son el **valor convertido** de la moneda del evento in-app a USD y luego a la moneda configurada en la aplicación.

Si no se especifica una moneda en el evento, **AppsFlyer usa USD por defecto**. El dashboard muestra el evento y los ingresos de la siguiente manera:

| Eventos In-App | Usuarios Únicos | Número de acciones | Ingresos |
| --- | --- | --- | --- |
| A | 1 | 1 | £234 |
| B | 1 | 1 | £149,4 - convertido de EUR a USD y luego a GBP. |
| C | 1 | 1 | £132,9 - predeterminado a USD ya que no se especifica ninguna moneda. Convertido directamente de USD a GBP. |

<div id="revenue-data-in-raw-data-reports" />

#### Datos de ingresos en reportes de raw data

Si configuras la moneda en **GBP** en la aplicación pero envías eventos in-app con diferentes monedas, los raw data muestran los ingresos tanto en la moneda de configuración de la aplicación como en la moneda del evento in-app.

Si configuras la moneda en **GBP** en la aplicación pero envías eventos in-app sin especificar la moneda, el reporte de raw data muestra los ingresos tanto en la moneda configurada en la aplicación como en USD.

El reporte de raw data de eventos in-app muestra el evento y los ingresos de la siguiente manera:

| Evento | Ingresos del evento | Moneda de ingresos del evento | Ingresos del evento en GBP |
| --- | --- | --- | --- |
| A | 234 | GBP | 234 |
| B | 171 | EUR | 149,4 - convertido de EUR a USD y luego a GBP. |
| C | 171 | USD (Dólar estadounidense) | 132,9 por defecto a USD ya que no se especifica ninguna moneda. Convertido directamente de USD a GBP. |

</Accordion>

<div id="sending-events" />

## Envío de eventos

Existen varias formas de enviar eventos in-app a AppsFlyer:

* <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">**SDK de AppsFlyer:**</Anchor> Esta es la forma más común de enviar eventos. Puedes enviar eventos in-app que registren las acciones de los usuarios en la aplicación usando la API de eventos in-app de AppsFlyer a nivel de SDK.
* <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">**Server-to-Server (S2S) API:**</Anchor> Usa la API de servidor a servidor (S2S) para enviar eventos que se produzcan fuera de la aplicación móvil, directamente a AppsFlyer. Por ejemplo, si tienes un usuario que es activo en ambas interfaces, web y móvil, puedes registrar eventos de ambas fuentes y atribuirlos al mismo usuario en AppsFlyer. Puede ser un evento in-app u otros eventos, como eventos en el sitio web, eventos de call-centers o compras en tu tienda física.
* <Anchor target="_blank" href="/marketers/es/docs/legacy-receipt-validation-for-in-app-purchases">**Validación de recibos**</Anchor>: Este es un mecanismo seguro donde la plataforma de pago, como Apple y Google, valida que la compra in-app se haya realizado tal y como se ha informado. La validación de compras es la herramienta principal para prevenir eventos de ingresos fraudulentos. También te ayuda a ver cuáles son los ingresos reales y filtra las compras in-app incompletas.
* <Anchor target="_blank" href="/marketers/es/docs/in-app-events-for-hybrid-apps">**Apps híbridas:**</Anchor> Estas aplicaciones combinan vistas nativas y contenido HTML, y también pueden registrar eventos in-app. Sin embargo, dado que el SDK solo puede enviar eventos desde el lado nativo, los desarrolladores deben reenviar todos los datos de eventos al código nativo.

<div id="setting-up-in-app-events" />

## Configuración de eventos in-app

El proceso para configurar eventos in-app requiere que el marketer y el desarrollador trabajen juntos de la siguiente manera:

| Paso | Rol | Tarea | Detalles |
| --- | --- | --- | --- |
| 1 | Comercializador | Determina los eventos in-app que quieres medir. [Define](/docs/in-app-events-overview#defining-an-inapp-event) y comunica los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#nombres-de-eventos-predefinidos">nombres de eventos</Anchor> y los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#parámetros-de-evento-predefinidos">parámetros de eventos</Anchor> a tu desarrollador. | Se recomienda comenzar con 3-5 eventos que puedas usar como KPI para medir la calidad de tus usuarios (por ejemplo, compras, registro y compartir). Los parámetros del evento son opcionales y puedes utilizar cualquier parámetro de evento con cualquier nombre de evento.<br /><br />Consulta [Eventos recomendados por sector empresarial](/docs/in-app-events-overview#recommended-events-by-business-vertical) para ver eventos in-app típicos. |
| 2 | desarrollador | Implementa el código en tu aplicación donde sea aplicable. | Los documentos para desarrolladores se encuentran <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">aquí</Anchor>. |
| 3 [Opcional] | Comercializador | Colabora con tu desarrollador para configurar el <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">campo de ID de usuario del cliente (CUID)</Anchor>. | Este campo ayuda a enriquecer los datos de eventos in-app cruzando los datos de atribución de AppsFlyer con tus otros datos usando el CUID como clave. |
| 4 [Opcional] | Comercializador | <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">Mapea eventos</Anchor> a partners relevantes en el dashboard. | Esta es una tarea continua, dependiendo de los partners con los que te integres. |

<Accordion title="Definición de un evento in-app">

Una vez que determines los eventos in-app que deseas medir, utiliza nuestro <Anchor target="_blank" href="https://evgen.appsflyer.com/">generador de eventos in-app</Anchor> para definir los eventos y parámetros de la siguiente manera:

1. Selecciona el nombre de evento que mejor se adapte al escenario que quieres registrar.
2. Selecciona los parámetros que desea asociar con el evento. Elige parámetros que proporcionen contexto adicional al evento y enriquezcan los datos.
3. Descarga el archivo finalizado desde el generador de eventos de la aplicación y compártelo con tu desarrollador.

<span id="h_01HDBZW9XFN2B8AC18VW99G8Z6"></span>**Ejemplo**

Un especialista en marketing de una app de eCommerce quiere registrar el tipo de contenido que ven los usuarios para comprender mejor qué categorías son las más populares y vincular las visualizaciones de productos con las ventas de productos.

La tabla siguiente muestra un ejemplo de la estructura del evento que el marketer proporciona al desarrollador:

<table><thead><tr><th>Nombre del evento</th><th>Parámetros del evento</th><th>Valores de los parámetros</th><th>¿Cuándo se activa el evento?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>Precio del producto</td><td rowspan="3"><span>Cuando un usuario visualiza la página de detalles de un producto específico</span></td></tr><tr><td><span>af_content_type</span></td><td><span>Nombre de la categoría del producto, como zapatos</span></td></tr><tr><td><span>af_content_id</span></td><td><span>ID del producto, por ejemplo, SKU</span></td></tr></tbody></table>

</Accordion>

<Accordion title="Eventos recomendados por sector empresarial">

La siguiente tabla proporciona enlaces a artículos con ejemplos y flujos de eventos típicos que recomendamos registrar por vertical.

| Vertical comercial | Título del artículo |
| --- | --- |
| <Image alt="Eventos_en_la_aplicación_juegos.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events">Eventos recomendados para aplicaciones de juegos</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events">Eventos recomendados para apps de comercio electrónico</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-entertainment-app-events">Eventos recomendados para apps de entretenimiento</Anchor> |
| <Image alt="bancos.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-finance-and-banking-app-events">Eventos recomendados para apps de banco y finanzas</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-p2p-lending-app-events">Eventos recomendados para aplicaciones de préstamos P2P</Anchor> |
| <Image alt="educación.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-online-education-app-events">Eventos recomendados para apps de educación online</Anchor> |
| <Image alt="Eventos_en_la_aplicación_paseo.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-ride-hailing-app-events">Eventos recomendados para apps de transporte compartido</Anchor> |
| <Image alt="Eventos_en_la_aplicación_vuelo.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-flight-booking-app-events">Eventos recomendados de la aplicación de reserva de vuelos</Anchor> |
| <Image alt="Eventos_InApp_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events">Eventos recomendados para apps de reserva de hoteles</Anchor> |
| <Image alt="5669_Icono_de_salud_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-healthcare-app-events">Eventos recomendados para apps de salud</Anchor> |
| <Image alt="icono_de_telecomunicaciones.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-telecommunication-app-events">Eventos recomendados para apps de telecomunicaciones</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-ewallet-app-events">Eventos recomendados para aplicaciones eWallet</Anchor> |
| <Image alt="balón_de_fútbol.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/es/docs/recommended-sports-betting-events">Eventos recomendados para apuestas deportivas</Anchor> |

</Accordion>

<Accordion title="Ver datos de eventos in-app">

Los eventos in-app se atribuyen a la fuente de medios que ha hecho posible la instalación durante toda la vida del usuario. Los datos de los eventos se presentan como <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Lifetime Value o Datos de Actividad</Anchor>.

Puedes consultar tus datos de eventos in-app en los siguientes lugares:

* Página general del dashboard: Muestra el rendimiento en tiempo real de la adquisición de usuarios (UA) en base al LTV. **Nota**: Esto incluye ingresos divididos entre usuarios orgánicos y no orgánicos reportados a través de eventos in-app, e ingresos por retargeting que se <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">atribuyen dos veces.</Anchor>
* Página de eventos: Muestra el rendimiento de eventos in-app LTV en todas las fuentes de medios
* <Anchor target="_blank" href="/marketers/es/docs/activity-dashboard">Página de actividad</Anchor>: Muestra las actividades in-app para el rango de fechas seleccionado.
* <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Reporte de raw data de eventos in-app</Anchor>: Muestra datos de actividad, es decir, una lista cronológica de las acciones realizadas por toda tu base de usuarios. Este reporte incluye valores de parámetros de eventos, por ejemplo:

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Ten en cuenta que el reporte de raw data es una función premium.

<div id="note-2" />

> 📘 **Nota:**
>
> Los valores de los parámetros de eventos in-app están disponibles exclusivamente en los reportes de eventos in-app en raw data. No se muestran en los Dashboards General, Evento o Actividad, ni en los reportes de datos agregados.

</Accordion>

<Accordion title="Consejos">

Ten en cuenta lo siguiente al definir nombres de eventos y parámetros en la app:

* Para mantener la coherencia de datos en los reportes de raw data, recomendamos definir y utilizar los mismos nombres y estructuras de eventos in-app en todas las plataformas.
* Usa un número mínimo de eventos para facilitar la comparación de la calidad de usuarios provenientes de diferentes fuentes.
* **Es crucial que garantices la privacidad de tus usuarios.** **Evita completar los valores de eventos in-app con datos restringidos que puedan identificarlos directamente.** **Por ejemplo, dirección de correo electrónico, nombre, número de identificación y, en algunos lugares, código postal. Para obtener más información sobre los datos restringidos, consulta la** <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">**política de privacidad de los servicios**</Anchor>.
* Ten en cuenta que AppsFlyer incluye la dirección IP de los dispositivos durante las <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">interacciones</Anchor>. En algunas jurisdicciones o escenarios de uso, la dirección IP puede considerarse información de identificación personal (PII). Usamos la dirección IP para determinar la ubicación geográfica general (ciudad, distrito) del dispositivo, pero no la dirección específica. Si es necesario, puedes optar por <Anchor target="_blank" href="/marketers/es/docs/apply-ip-masking-to-user-data">enmascarar las direcciones IP</Anchor> para que no aparezcan en los reportes de raw data.
* Los eventos in-app son la única fuente de datos de ingresos en AppsFlyer. Puedes asignar un valor específico de ingresos a cada evento y visualizarlo en el dashboard de tu aplicación. Saber más sobre los [parámetros de monetización](/docs/in-app-events-overview#revenue-events). ![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)

</Accordion>

<Accordion title="Limitaciones">

Ten en cuenta lo siguiente al definir nombres de eventos y parámetros en la app:

* Recomendamos usar solo caracteres alfanuméricos en minúscula (a-z y 0-9) para los nombres de eventos in-app. Los nombres de los eventos distinguen entre mayúsculas y minúsculas, lo que significa que af\_purchase y af\_PURCHASE son dos eventos diferentes en los raw data. Sin embargo, en los informes y dashboards agregados (por ejemplo, General o Eventos), solo se permiten letras minúsculas y, por lo tanto, se pueden mostrar como un solo evento.
* Existe un límite de cardinalidad de 300 eventos únicos por día. <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">Saber más</Anchor>
* Los usuarios únicos solo se cuentan para los primeros 100 eventos después de instalar la aplicación.
* Los nombres de eventos no pueden comenzar con estos caracteres: " = + -
* Los valores de evento no deben contener el carácter +, salvo URLs codificadas o según <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>.
* Los nombres de eventos no pueden contener espacios vacíos. Puede utilizar guiones bajos antes o después del nombre del evento.
* Los valores de los eventos no deben exceder los 2000 caracteres para evitar que se acorten en los reportes de raw data. Sin embargo, si el evento se origina en el SDK, se recomienda mantenerlo por debajo de los 1000 caracteres para asegurarse de que la carga útil no se trunque al enviarse en la solicitud HTTP.
* Si incluyes la URL de referencia como valor de evento, debe estar <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">codificada como URL</Anchor>.
* Meta Ads tiene algunas limitaciones con respecto a los nombres y parámetros de los eventos. Lee sobre las limitaciones <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">aquí</Anchor>.

</Accordion>

<div id="faq" />

## Preguntas frecuentes

La siguiente sección incluye varias preguntas frecuentes sobre eventos in-app.

<Accordion title="¿Cómo uso el parámetro de ingresos?">

Puedes enviar valores de ingresos con cualquier nombre de parámetro y evento. Sin embargo, para registrar los ingresos (incluidos los [ingresos negativos](/docs/in-app-events-overview#revenue-events)) en los datos sin procesar y agregados de AppsFlyer, debes usar el parámetro `af_revenue`. Utilízalo siempre con eventos in-app que representen la generación de ingresos reales en tu lógica comercial.

`af_currency` representa la divisa utilizada en `af_revenue` (o en `af_price`). Si falta `af_currency` en los parámetros del evento, AppsFlyer lo envía con el valor predeterminado "USD". Para más información sobre el parámetro `af_revenue`, consulta la [guía de atribución de ingresos](/docs/in-app-events-overview#revenue-events).

Si también quieres reportar ingresos aplicando tu propia lógica, por ejemplo, después de comisiones e impuestos, envía `af_net_revenue` como parámetro personalizado junto con `af_revenue`. `af_net_revenue` no sustituye a `af_revenue`. Para más información, consulta [Ingresos netos](#net-revenue).

</Accordion>

<Accordion title="¿Cómo atribuye AppsFlyer los eventos?">

Los eventos in-app se atribuyen a la fuente original de medios de la instalación de la app.

Al instalar una app (primer lanzamiento de la aplicación), AppsFlyer utiliza varios <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">métodos de atribución</Anchor> para determinar la atribución de la instalación. Al mismo tiempo, el SDK de AppsFlyer genera un nuevo <Anchor target="_blank" href="/marketers/es/docs/about-device-identifiers#appsflyer-id">ID de AppsFlyer</Anchor> único, que se asocia con los detalles de atribución.

Cada evento posterior dentro de la aplicación realizado por el mismo dispositivo utiliza este ID. Esto permite a AppsFlyer atribuir el evento a la fuente de medios original. Los anunciantes pueden usar esto para seguir la trayectoria completa del usuario en su aplicación.

Los eventos de usuarios a los que se ha hecho retargeting recientemente pueden tener <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución</Anchor>.

AppsFlyer considera los eventos de instalaciones atribuidas como **orgánicos** cuando:

* Los términos de la fuente de medios [exigen la eliminación de los datos a nivel de usuario](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations).
* El usuario borra los datos de la aplicación almacenados en el dispositivo, obligando a crear un nuevo ID de AppsFlyer.

</Accordion>

<Accordion title="¿Se registran los eventos si un dispositivo está desconectado?">

Si un usuario inicia un evento sin conexión a internet, AppsFlyer aún puede registrarlo. Este es el procedimiento:

1. El SDK envía los eventos a los servidores de AppsFlyer y espera una respuesta exitosa.
2. Si el SDK no recibe una respuesta exitosa, el evento se guarda en caché.
3. Una vez que se recibe la siguiente respuesta exitosa, el evento almacenado se envía nuevamente al servidor.
4. Si hay múltiples eventos en la caché, se envían al servidor uno tras otro.

<div id="note-3" />

> 📘 **Nota:**
>
> El caché del SDK puede almacenar hasta 40 eventos, lo que significa que solo se guardan los primeros 40 eventos que ocurren sin conexión. Todo lo que se genera posteriormente, hasta la siguiente respuesta exitosa, se elimina.
>
> La hora del evento que aparece en los raw data es cuando el evento se envía a AppsFlyer después de que el dispositivo se conecte nuevamente. No es el momento preciso en el que ocurre el evento.

</Accordion>

<Accordion title="¿Qué son los eventos complejos in-app y cómo los configuro?">

Los eventos complejos dentro de la aplicación permiten enviar múltiples eventos en una sola llamada API. Son útiles cuando se desea ver varias acciones de usuario estrechamente relacionadas agrupadas (por ejemplo, añadir varios productos a la cesta en una sola sesión).

Recomendamos usar el objeto `af_order_info` para enviar eventos in-app complejos a ad network compatibles. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/item-level-order-data-for-ad-networks-af-order-info">Datos de pedidos a nivel de artículo para ad network (af\_order\_info)</Anchor>.

**Ejemplo** (formato recomendado: un campo por array de artículos):

```json
{
  "af_order_info": {
    "sku": ["ID1", "ID2", "ID3"],
    "revenue": [4.99, 9.99, 2.50],
    "qty": [1, 1, 2]
  }
}
```

Consulta <Anchor target="_blank" href="/marketers/es/docs/item-level-order-data-for-ad-networks-af-order-info">Datos de pedidos a nivel de artículo para ad network (af\_order\_info)</Anchor> para ver la lista completa de campos (hasta 7 campos por artículo) y el formato alternativo de un objeto por artículo.

Como alternativa, también puedes estructurar el evento con `af_content` como un array JSON. Cada objeto de la matriz debe incluir `id` y `quantity`. `af_content_list` es opcional y puede omitirse.

<span id="h_01KSMX2ECGTDXQP3G9PZW1PFQD"></span>**Ejemplo**

```json
{
  "af_revenue": 4.99,
  "af_currency": "USD",
  "af_order_id": "12345",
  "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
}
```

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> Si la string `af_content` supera los 1.000 caracteres, AppsFlyer podría enviar el evento a Meta sin el parámetro `fb_content`. Si en ese caso tampoco está presente `af_content_list`, Meta no recibe datos de identificación de producto. Mantén `af_content` por debajo de 1.000 caracteres en los eventos que incluyan muchos elementos.

Para más información sobre los eventos complejos de Meta Ads, consulta <Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping#envía-eventos-in-app-complejos-a-meta-ads">Enviar eventos complejos en la aplicación a Meta Ads</Anchor>.

**Nota:** En <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#limitations">Audiences</Anchor> de AppsFlyer, los array no son compatibles dentro de los atributos de evento; solo se admiten números o string.

</Accordion>

<Accordion title="¿Puedo agregar varios artículos a una sola transacción?">

Sí, puedes agregar varios artículos a una sola transacción. En lugar de valores únicos por parámetro de evento, puedes tener un conjunto de elementos que describa la transacción, separados por comas. El formato debe ser una cadena JSON.

<span id="h_01HDBZW9XFB9TAT8W4CGNP1892"></span>**Ejemplo**

En la misma transacción, el Sr. Smith compra dos camisas idénticas, un par de zapatos y un sombrero en una tienda online de Estados Unidos. La secuencia en la que se enumera cada artículo debe ser idéntica para cada uno

```json
"{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
```

Los múltiples artículos se envían como un conjunto en <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">postbacks</Anchor>. Por el momento, los anuncios de Meta y X Ads no pueden analizar correctamente los parámetros de los conjuntos. Para ayudar con este problema, AppsFlyer suma el número de artículos (`af_quantity`) en lugar de enviarlo a estas redes de autorreporte (SRN) como un array. En nuestro ejemplo, los anuncios de Meta recibirían `af_quantity=4`.

<div id="notes" />

> 📘 **Notas**
>
> * En <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#limitations">Audiences</Anchor> de AppsFlyer, los array no son compatibles dentro de los atributos de evento; solo se admiten números o string.
> * Se pueden usar varios artículos con los siguientes eventos in-app:
>   `af_add_to_cart`, `af_add_to_wishlist`, `af_tutorial_completion`, `af_initiated_checkout`, `af_purchase`, `af_rate`, `af_spent_credits`, `af_content_view`, `af_travel_booking`, `af_update`

</Accordion>

<Accordion title="¿Cómo gestiona AppsFlyer la deduplicación de eventos?">

Contamos con un mecanismo de deduplicación de eventos in-app. Revisa todos los eventos in-app para ver si hubo algún evento in-app idéntico que provino del mismo appsflyer\_id hace menos de 10 segundos. Si se encuentra un evento así, el mecanismo elimina el duplicado.

Dos eventos se consideran idénticos si los siguientes campos en ambos eventos son los mismos:

* Nombre del evento
* Valor del evento
* Identificación de la aplicación
* Identificación de AppsFlyer

<div id="note-4" />

> 📘 **Nota:**
>
> La deduplicación solo funciona para los eventos in-app enviados desde el SDK.
>
> Los eventos in-app S2S no se deduplican.

</Accordion>

<Accordion title="¿Durante cuánto tiempo conserva AppsFlyer los datos a nivel de usuario y cuáles son las obligaciones de eliminación?">

AppsFlyer retiene raw data a nivel de usuario según el tipo de integración y los requisitos del partner. Los datos agregados pueden conservarse hasta cinco años.

Los períodos de retención pueden variar según las fuentes de medios y los métodos de entrega (por ejemplo, Data Locker o Pull API), y pueden cambiar debido a obligaciones legales, contractuales o de partners.

Después de la eliminación, los eventos relacionados con los usuarios eliminados se muestran como orgánicos. Los datos agregados pasados no se modifican. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention#obligaciones-de-conservación-y-eliminación-de-datos">Obligaciones de retención y eliminación de datos</Anchor>.

</Accordion>

<Accordion title="¿Necesito agregar el parámetro OS (sistema operativo) a mis eventos?">

* El SDK de Android y el SDK de iOS agregan automáticamente el parámetro OS (sistema operativo).
* Para la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor>, a partir del 1 de julio de 2021, deberá enviar el parámetro OS (sistema operativo) para las aplicaciones iOS. Si no envías este parámetro, se considerará que los datos provienen de un usuario de iOS 14.5 y esto afecta la forma en que se <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">ponen a disposición los raw data</Anchor>.

</Accordion>

<Accordion title="¿Cómo puedo garantizar la deduplicación de eventos por parte del partner?">

Si el mismo evento también se carga directamente en la red (por ejemplo, desarrollando internamente soporte para la API de conversiones del partner), puedes asegurarte de que el partner pueda deduplicar el evento enviando un `event_id` similar tanto a través de la integración directa de CAPI como a través de AppsFlyer. Para hacerlo, asegúrate de incluir un campo llamado «af\_customer\_event\_id» dentro del campo `event_value` y de enviar el mismo valor en el campo `event_id` que se envía directamente al partner desde el lado del anunciante.

Esta solución es compatible con `metaweb_int`, `tiktokweb_int`, `snapweb_int`, `pinterest_int`  y `pinterest_int`.

</Accordion>

<div id="see-also" />

## Véase también

* <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Configuración de postbacks de datos de eventos in-app</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=por-qu%C3%A9-registrar-eventos-in-app h_01HDBZW9XEBTY13MG4AN93RNCD=por-qu%C3%A9-registrar-eventos-in-app about-inapp-events=sobre-los-eventos-in-app h_01HDBZW9XEBDSDA9T5X5B6KGTG=sobre-los-eventos-in-app h_01HDBZW9XE3Z40JE9576C4XSF4=consejo predefind-and-custom-events=eventos-predefinidos-y-personalizados 01J9XGXGC7R9B19MMX4CQV7DAY=eventos-predefinidos-y-personalizados revenue-in-inapp-events=ingresos-en-eventos-in-app 01J9XGXGC990R3AG0R0XT9E5Y7=ingresos-en-eventos-in-app h_01M43GXKW5NCRE5MJG45EG9AYX=nota h_NETREVENUE0002=nota-1 currency-conversion=conversi%C3%B3n-de-moneda h_01HDBZW9XEMGA5RAW0DBBPV3FQ=conversi%C3%B3n-de-moneda currency-display=visualizaci%C3%B3n-de-la-moneda h_01HDBZW9XE85YC3JHG58YYAB8F=visualizaci%C3%B3n-de-la-moneda revenue-data-in-the-dashboard=datos-de-ingresos-en-el-dashboard h_01HDBZW9XEVWB9045N0YEVWE6Z=datos-de-ingresos-en-el-dashboard revenue-data-in-raw-data-reports=datos-de-ingresos-en-reportes-de-raw-data h_01HDBZW9XEGYFD3W9FT1N3ZGQW=datos-de-ingresos-en-reportes-de-raw-data sending-events=env%C3%ADo-de-eventos h_01HDBZW9XFESG6MP9QF1XCJKE6=env%C3%ADo-de-eventos setting-up-inapp-events=configuraci%C3%B3n-de-eventos-in-app h_01HDBZW9XF13AGRCN2HJ18RHS2=configuraci%C3%B3n-de-eventos-in-app 01JEWW8YB6A91VT8Z4PM9NCV00=nota-2 faq=preguntas-frecuentes h_01HDBZW9XF5H24H2HCJKKHCRTE=preguntas-frecuentes h_01HDBZW9XFCDMKNWJ75AWHC2Y0=nota-3 h_01KSMX2ECGNMX39RD2F6ZHQEK4=dos-puntos- h_01HDBZW9XFJ68WSM3066NVRATS=notas h_01HDBZW9XFWKN7W90PSVMX73FS=nota-4 h_01HDNZ708FN0N286R5HDQGMNGZ=v%C3%A9ase-tambi%C3%A9n" />
