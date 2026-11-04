---
title: Configuración de la campaña de Baidu mDSP Ads (Baiyi)
metadata:
  keywords:
    - Advertisers
    - Baidu mDSP
    - Baiyi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-24T07:22:04Z'
  edited_at: '2026-09-17T00:25:59Z'
  id: 115004330446
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115004330446
---
> **De un vistazo:** Baidu mDSP Ads (Baiyi), un partner integrado de ad network de AppsFlyer, es un proveedor de soluciones publicitarias y forma parte de Baidu, el motor de búsqueda dominante en China con más del 70% de cuota de mercado.

<div id="setting-up-baidu-mdso-ads-baiyi" />

## Configurar Baidu mDSP Ads (Baiyi)

1. En AppsFlyer, en el menú lateral, selecciona **Collaborate** **> Partner Integrations** > **Partner Marketplace**.
2. Busque al socio y selecciónelo. Se te dirigirá a la página de configuración de la integración.

La ventana de configuración de Baidu mDSP Ads (Baiyi) incluye 2 pestañas activas: integración y enlace de atribución. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita**, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Baidu mDSP Ads (Baiyi) tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

![baidu-mdsp-default-postbacks.png](https://files.readme.io/fdde731527468b9837efa2230c5416f3393024b8c4eec8b44339086a2f31b984-360002069005.png)

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes mapear tus eventos de AppsFlyer con Baidu mDSP Ads (Baiyi) a través de postbacks.

![baidu-mdsp-in-app-events.png](https://files.readme.io/fa515fac11e82be11bb55bb9b198ac63681ecdb713f0f6537f4ca7bf0c60e5b1-360002069085.png)

1. Activa los Postbacks de eventos in-app con el selector.
2. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
3. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o el ID de cada evento, tal como se define del lado de Baidu mDSP Ads (Baiyi).  <br />Obtén el ID de evento correspondiente de Baidu mDSP Ads (Baiyi) e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Baidu mDSP Ads (Baiyi) para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Baidu mDSP Ads (Baiyi). Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar diferentes campañas en ejecución con Baidu mDSP Ads (Baiyi).  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Baidu mDSP Ads (Baiyi).  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos de campañas específicas de Baidu mDSP Ads (Baiyi).  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio**: configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura de enlaces de atribución de AppsFlyer y sus parámetros**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Baidu mDSP Ads (Baiyi).

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

![baidu-mdsp-click-through.png](https://files.readme.io/19f6616cc1e62ec8888a72625ce936acdb6e8e63e4a4cd4273cdc99fd2297a93-360002075089.png)

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Baidu mDSP Ads (Baiyi) para activarlo cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de los ingresos por publicidad no está disponible para Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

La configuración de permisos no está disponible para Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="create-conversion-rule-at-baidu-mdsp-ads" />

## Crea una regla de conversión en Baidu mDSP Ads

Inicia sesión en Baidu mDSP Ads en http://baiyi.baidu.com/ y ve a **Tool** >> **Apps**:

![mDSP_4.png](https://files.readme.io/90f99229f6bffe9b9edbf0469f9b4e66ca9c5c55184eb542e250ef6a9bd76aee-115014006086.png)

Haz clic en **Crear nueva app**.

![mDSP_5.png](https://files.readme.io/c034e3238fbd6021fefc44ff8b1cf8b4d39c3f9043b02074c3bdccce2747ac48-115014006106.png)

Introduce toda la información relevante en los campos.

Añade el enlace de atribución de AppsFlyer **en el cuadro de Feedback URL**:

![mDSP_6.png](https://files.readme.io/6692275131ee49b62febcb558457f7f1a1fbd167f3d3f61d976e1cb248a61388-115014006906.png)

***NOTA***: En las aplicaciones de iOS, añade la aplicación introduciendo el **Appid**. En las aplicaciones de Android, añade la aplicación de dos formas:  
1. Conectándola con la aplicación que has subido a la plataforma de desarrolladores de Baidu ([http://app.baidu.com/](http://app.baidu.com/)), o  
2. Accediendo a la página de descarga del APK o subiendo allí el APK.

Después, haz clic en el botón de envío al final de la página.

2. Crea anuncios de promoción de apps en Baidu mDSP Ads.

Haz clic en **Campaign Management** >> **Create New Campaign**:

![mDSP_7.png](https://files.readme.io/aab8866a1969e403247c97018aae1d65d456ce4e261412035ef91a1862f509b9-115014006926.png)

En la sección **2. Configura la unidad de anuncio** >> Ve a **Objetivos**, elige Instalación de la app >> Completa el resto de la información relacionada y envía la campaña de anuncios para su verificación:

![mDSP_8.png](https://files.readme.io/da064e6811b4c749a20757d711186dc705070629887cdf2e7b514cc17274af75-115014006946.png)

<div data-zendesk-anchors="setting-up-baidu-mdso-ads-baiyi=configurar-baidu-mdsp-ads-baiyi h_01HKW6TN4YBTMR1ZDH77D7SK7N=configurar-baidu-mdsp-ads-baiyi h_01HKW6TN4YM927W1VAKNWFQ0SJ=integration-tab activate-partner=activar-socio h_01HKW6TN4Y4EXABZTJ2VE4QRTK=activar-socio inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6TN4YYDKNGCSJB4MARK52=configuraci%C3%B3n-de-eventos-in-app h_01HKW6TN4Y2D2K419172AZJXR6=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6TN4YQTMGSMPGR01FR658=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6TN4Y9ZP7SXMTD0XGNPGV=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6TN4Y5A1PT6RCVCFYRG9Q=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6TN4Z02V726B7379TMBC0=cost-tab h_01HKW6TN4Z01YZWHMGF5N1KC50=ad-revenue-tab h_01HKW6TN4Z3KCEFDW9YA2A2BZV=permissions-tab create-conversion-rule-at-baidu-mdsp-ads=crea-una-regla-de-conversi%C3%B3n-en-baidu-mdsp-ads h_01HKW6TN4ZWEA7683C8MFAT4AY=crea-una-regla-de-conversi%C3%B3n-en-baidu-mdsp-ads" />
