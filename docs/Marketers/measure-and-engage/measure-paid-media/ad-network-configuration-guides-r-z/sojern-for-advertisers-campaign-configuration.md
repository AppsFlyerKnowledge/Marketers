---
title: Configuración de campañas de Sojern para anunciantes
metadata:
  keywords:
    - Advertisers
    - Sojern
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-07T08:59:30Z'
  edited_at: '2026-09-11T00:24:49Z'
  id: 360001378265
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/360001378265
---
> **De un vistazo:** Sojern for Advertisers, un partner integrado de ad network de AppsFlyer, se especializa en la compra programática para el mercado de viajes.

Para configurar tus campañas con Sojern for Advertisers, sigue los pasos a continuación.

<div id="setting-up-sojern-for-advertisers" />

## Configuración de Sojern for Advertisers para anunciantes

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás activar el interruptor ***Activar partner*** para habilitar la configuración de los parámetros de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Sojern for Advertisers prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Sojern for Advertisers.

<div id="general-settings" />

### Configuración general

**ID de socio**

Sojern for Advertisers se conecta con AppsFlyer a través de un ID de partner único. Si todavía no tienes el ID de partner, debes obtenerlo de Sojern for Advertisers para continuar con la integración.

![Sojern_msc_new_2.png](https://files.readme.io/35d02000642f8dc768c5bd1b0ca7846b9575900b2e9b3169673840f438815ef1-360002443905.png)

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Sojern for Advertisers después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que provienen únicamente de usuarios atribuidos a Sojern for Advertisers.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para reportarla a Sojern for Advertisers.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Sojern for Advertisers mediante postbacks.

1. Introduce de nuevo el ID de partner de Sojern for Advertisers.
2. Activa los Postbacks de eventos in-app con el selector.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.  
   Para obtener más información sobre los eventos in-app de Sojern for Advertisers, haz clic aquí.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según se define del lado de Sojern for Advertisers.  <br />Obtén el ID de evento correspondiente de Sojern for Advertisers y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

<div id="event-types" />

### Tipos de evento

Sojern for Advertisers requiere la implementación de los siguientes eventos:

**Hotel**

| Tipo de evento | Eventos de Sojern for Advertisers | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | PÁGINA\_DE\_INICIO | af\_app\_opened | La aplicación se abre o se trae al primer plano |
| Resultado de la búsqueda | BÚSQUEDA\_DE\_HOTEL | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | PRODUCTO\_DE\_HOTEL | af\_content\_view | Vista de un producto/opción específico de los resultados de búsqueda |
| Confirmación | CONFIRMACIÓN\_DE\_HOTEL | af\_compra | Compra del/de los artículo(s) |

**Vuelo**

| Tipo de evento | Eventos de Sojern para anunciantes | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | PÁGINA\_DE\_INICIO | af\_app\_opened | La aplicación se abre o se trae al primer plano |
| Resultado de la búsqueda | BÚSQUEDA\_DE\_VUELO | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | PRODUCTO\_DE\_VUELO | af\_content\_view | Vista de un producto/opción específico de los resultados de búsqueda |
| Confirmación | CONFIRMACIÓN\_DE\_VUELO | af\_compra | Compra del/de los artículo(s) |

**Crucero**

| Tipo de evento | Eventos de Sojern para anunciantes | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | HOME\_PAGE | af\_app\_opened | Apertura de la aplicación o paso a primer plano |
| Resultado de la búsqueda | CRUISE\_SEARCH | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | CRUISE\_PRODUCT | af\_content\_view | Vista de un producto u opción específicos de los resultados de la búsqueda |
| Confirmación | CRUISE\_CONFIRMATION | af\_compra | Compra del/de los artículo(s) |

**Coche**

| Tipo de evento | Eventos de Sojern para anunciantes | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | HOME\_PAGE | af\_app\_opened | Apertura de la aplicación o paso a primer plano |
| Resultado de la búsqueda | CAR\_SEARCH | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | CAR\_PRODUCT | af\_content\_view | Vista de un producto u opción específicos de los resultados de la búsqueda |
| Confirmación | CAR\_CONFIRMATION | af\_compra | Compra de los artículo(s) |

**Entretenimiento**

| Tipo de evento | Eventos de Sojern para anunciantes | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | HOME\_PAGE | af\_app\_opened | Apertura de la aplicación o paso al primer plano |
| Resultado de búsqueda | ENTERTAINMENT\_SEARCH | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | ENTERTAINMENT\_PRODUCT | af\_content\_view | Vista de un producto u opción específicos a partir de los resultados de búsqueda |
| Confirmación | ENTERTAINMENT\_CONFIRMATION | af\_compra | Compra de los artículo(s) |

**Tren**

| Tipo de evento | Eventos de Sojern para anunciantes | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | HOME\_PAGE | af\_app\_opened | Apertura de la aplicación o paso al primer plano |
| Resultado de búsqueda | RAIL\_SEARCH | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | RAIL\_PRODUCT | af\_content\_view | Vista de un producto/opción específico de los resultados de búsqueda |
| Confirmación | RAIL\_CONFIRMATION | af\_compra | Compra del/de los artículo(s) |

**Vacaciones**

| Tipo de evento | Eventos de Sojern for Advertisers | Evento del SDK | Nota |
| --- | --- | --- | --- |
| Página de inicio | HOME\_PAGE | af\_app\_opened | La app se abre o pasa al primer plano |
| Resultado de búsqueda | VACATION\_SEARCH | af\_list\_view | Página de resultados de búsqueda que muestra una lista de opciones |
| Producto | VACATION\_PRODUCT | af\_content\_view | Vista de un producto/opción específico de los resultados de búsqueda |
| Confirmación | VACATION\_CONFIRMATION | af\_compra | Compra del/de los artículo(s) |

<div id="correct-configuration-of-in-app-events" />

#### Configuración correcta de los eventos in-app

Al configurar una campaña con Sojern for Advertisers, es importante definir eventos in-app específicos.

Cuando la convención de nombres de AppsFlyer no esté disponible, usa la clave Param de Sojern for Advertisers.

Sojern for Advertisers tiene cuatro tipos de eventos in-app:

* Confirmación
* Producto
* Búsqueda
* Carrito

A continuación se muestra un ejemplo de la búsqueda y la confirmación para el sector de hoteles y vuelos:

|  | Nombre | Clave de parámetro | Nombre del evento in-app enriquecido de AppsFlyer |
| --- | --- | --- | --- |
| **Búsqueda de vuelos** | Tipo de evento | et | valor «fs» |
|  | Número de viajeros | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Número de niños | tch | af\_num\_children |
|  | Clase de servicio | fc | af\_class |
|  | Solo ida | fow | N/D |
|  | Multiciudad | fmc | N/D |
|  | Dominio del país del sitio web | dctry | N/D |
|  | Dominio del sitio | dominio | N/D |
|  | Aeropuerto de origen | fa1 | af\_destination\_a |
|  | Aeropuerto de destino | fa2 | af\_destination\_b |
|  | Ciudad de destino | fc1 | af\_city |
|  | Ciudad de origen | fc2 | N/D |
|  | Fecha de salida | fd1 | af\_departing\_departure\_date |
|  | Fecha de regreso | fd2 | af\_returning\_departure\_date |
| **Confirmación del vuelo** | Nombre | Clave de parámetro |  |
|  | Tipo de evento | et | valor 'fc' |
|  | Número de viajeros | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Número de niños | tch | af\_num\_children + af\_num\_infants |
|  | Clase de servicio | fc | af\_class |
|  | Dominio del país del sitio web | dctry | N/D |
|  | Dominio del sitio | dominio | N/D |
|  | Aeropuerto de origen | fa1 | af\_destination\_a |
|  | Aeropuerto de destino | fa2 | af\_destination\_b |
|  | Ciudad de destino | fc1 | af\_city |
|  | Ciudad de origen | fc2 | N/D |
|  | Fecha de salida | fd1 | af\_departing\_departure\_date |
|  | Fecha de regreso | fd2 | af\_returning\_departure\_date |
|  | Moneda de compra | fcu | af\_currency |
|  | Precio de compra | fp | af\_revenue |
| **Búsqueda de hoteles** | Nombre | Clave de parámetro |  |
|  | Tipo de evento | et | valor "hs" |
|  | Dominio del país del sitio web | dctry | af\_country |
|  | Ciudad de destino | hc1 | af\_city |
|  | Fecha de entrada | hd1 | af\_date\_a |
|  | Fecha de salida | hd2 | af\_date\_b |
|  | Número de viajeros | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Número de niños | tch | af\_num\_children + af\_num\_infants |
|  | Dominio del sitio | dominio | N/D |
| **Confirmación del hotel** | Nombre | Clave de parámetro |  |
|  | Tipo de evento | et | valor 'hc' |
|  | Dominio del país del sitio web | dctry | N/D |
|  | Ciudad de destino | hc1 | af\_city |
|  | Fecha de entrada | hd1 | af\_date\_a |
|  | Fecha de salida | hd2 | af\_date\_b |
|  | Número de viajeros | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Número de niños | tch | af\_num\_children + af\_num\_infants |
|  | Dominio del sitio | dominio | N/D |
|  | País de destino | hn1 | af\_country |
|  | Precio de compra | hp | af\_revenue |
|  | Moneda de compra | hcu | af\_currency |

<div id="example" />

> 📄 **Ejemplo**
>
> Valores del evento de búsqueda de vuelos:
>
> Evento in-app: af\_list\_view, valores del evento in-app: et=‘fs’&af\_num\_adults=`{number of adults}&af_num_children={number of children}&af_class={service class}&fow={one way}&fmc={multi city}&dctry={website country domain}&af_destination_a={departure airport code}&af_destination_b={arrival airport code}&af_city={destination city}&fc2={origin city}&af_departing_departure_date={YYYY-MM-DD}&af_returning_departure_date={YYYY-MM-DD}`

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Sojern for Advertisers para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Sojern for Advertisers.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Sojern for Advertisers.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de conjuntos de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Sojern for Advertisers.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio**: configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te aconsejamos limitar el número de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros del enlace de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeros inicios) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Sojern for Advertisers.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Sojern for Advertisers para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Sojern for Advertisers.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de la pestaña de ingresos no está disponible para Sojern for Advertisers.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

No hay disponible ninguna configuración de permisos para Sojern for Advertisers.

</Accordion>

<div data-zendesk-anchors="setting-up-sojern-for-advertisers=configuraci%C3%B3n-de-sojern-for-advertisers-para-anunciantes h_01HJS0FHZ6KE2Z93F3SWGEM5B8=configuraci%C3%B3n-de-sojern-for-advertisers-para-anunciantes h_01HJS0FHZ7Z9H58D8SWRCM64JH=integration-tab activate-partner=activar-socio h_01HJS0FHZ7SZ1EPN7PDH7EYP0T=activar-socio h_01HJS0FHZ778T3QF4XNM8FCHX0=nota general-settings=configuraci%C3%B3n-general h_01HJS0FHZ7EEAGSCDM4XXJVYC3=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJS0FHZ78EV1K8DVKN50VJ0B=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJS0FHZ7AN3ZQYF4ZS3X4BVT=configuraci%C3%B3n-de-eventos-in-app event-types=tipos-de-evento h_01HJS0FHZ7EVPMN25Y1985NFSS=tipos-de-evento correct-configuration-of-inapp-events=configuraci%C3%B3n-correcta-de-los-eventos-in-app h_01HJS0FHZ8807QADT9Z35NAWFT=configuraci%C3%B3n-correcta-de-los-eventos-in-app h_01HJS0FHZ9J3MWRKF2YCWZ611Z=ejemplo h_01HJS0FHZ9ASEYGFWZ681EMZ47=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJS0FHZ9YVAG37CQQK33RNJ2=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJS0FHZ9R2SM91Y5WBP002M1=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJS0FHZ9GVGWJEPJ337B1DHE=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJS0FHZ9BXJHQWC9CQWNVANS=cost-tab h_01HJS0FHZ9TARRTF5WZZ6P2V30=ad-revenue-tab h_01HJS0FHZ9J271QZ8SKXKY6Z67=permissions-tab" />
