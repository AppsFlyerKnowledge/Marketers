---
title: Configuración de la campaña de anuncios de WeChat
metadata:
  keywords:
    - Wechat Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-09-17T00:26:31Z'
  id: 115003044106
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115003044106
---
> **Resumen:** Aprende a medir tus campañas con WeChat en AppsFlyer.

## Introducción

WeChat, uno de los Partners integrados de AppsFlyer, es una app china multipropósito de mensajería, redes sociales y pagos móviles desarrollada por Tencent.

Para configurar tus campañas con WeChat, sigue los pasos a continuación.

## Configurar tu campaña en WeChat

Antes de continuar con la integración de WeChat en AppsFlyer, configura la campaña en WeChat.

En WeChat, haz lo siguiente:

1. Rellena y verifica la clave de Tencent
2. Elige el tipo de conversión de la lista:

   * Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
   * Registrarse.
   * Compra
   * Agregar al carrito

   Ten en cuenta que WeChat solo permite un objetivo de conversión por aplicación.
3. Introduce la [URL de atribución de clics](#attribution-link-tab) de AppsFlyer

![wechat-configuration.png](https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png)

Cuando hayas introducido esta información, confírmala haciendo clic en el botón resaltado. En el siguiente paso, recibirás la *encrypt \_key* y la *sign\_key*:

![wechat-keys.png](https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png)

Copia las claves y úsalas al configurar la campaña en AppsFlyer.

### Configurar una campaña de WeChat como agencia

Las agencias tienen distintos tipos de cuenta en WeChat. Según el tipo de cuenta, algunas agencias pueden crear objetivos de conversión y otras no.

Si tu cuenta te permite crear un objetivo de conversión, puedes continuar siguiendo las instrucciones anteriores.

Si no tienes permiso para crear un objetivo de conversión, en WeChat puedes ver un objetivo creado por otra cuenta que gestiona la misma aplicación. En este caso, pide al anunciante que te proporcione la *encrypt \_key* y la *sign\_key* y úsalas para configurar la campaña en AppsFlyer.

## Configurar WeChat en AppsFlyer

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Más información</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación.

La ventana de configuración de WeChat incluye 4 pestañas: Integración, Enlace de atribución, Enriquecimiento de datos y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, WeChat prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a WeChat.

### Configuración general

**ID de socio**

WeChat se conecta con AppsFlyer mediante tres parámetros únicos:

1. ID de Sign
2. ID de la App de WeChat
3. Clave de cifrado

Si aún no tienes el ID de firma, el ID de aplicación de WeChat y la clave de cifrado, debes obtenerlos de WeChat para continuar con la integración.

<Image alt="wechat-integration-general-settings.png" src="https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png" width="390px" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a WeChat después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

![wechat-default-postbacks.png](https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png)

Selecciona **Solo eventos** **atribuidos a este partner** para eventos que provengan únicamente de usuarios atribuidos a WeChat.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para reportarse a WeChat.

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a WeChat mediante postbacks.

![wechat_in_app_event_postbacks.png](https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png)

1. Introduce de nuevo la clave de cifrado.
2. Introduce el ID de firma
3. Ingresa el ID de la App de WeChat
4. Activa los postbacks de eventos in-app.
5. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
6. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
7. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento, tal como se define del lado de WeChat.  <br />Obtén el ID de evento correspondiente de WeChat e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a WeChat para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de WeChat. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: agrégala para comparar diferentes campañas en ejecución con WeChat.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de WeChat.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define los nombres de los conjuntos de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de WeChat.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros de enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros de enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![parámetros-de-enlace-de-atribución.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a WeChat.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

[![](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a WeChat para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Activa la integración de costos de Tencent para recibir datos de costo de WeChat.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

No hay ninguna configuración de permisos disponible para este partner.

</Accordion>

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HKW6Z36NGCWC0R6EQX49S34J=introducci%C3%B3n setting-up-your-campaign-on-wechat=configurar-tu-campa%C3%B1a-en-wechat h_01HKW6Z36NTSGCDQM553YMHHDH=configurar-tu-campa%C3%B1a-en-wechat setting-up-wechat-campaign-as-an-agency=configurar-una-campa%C3%B1a-de-wechat-como-agencia h_01HKW6Z36N8S8KSBNMR8A54RRN=configurar-una-campa%C3%B1a-de-wechat-como-agencia setting-up-wechat-on-appsflyer=configurar-wechat-en-appsflyer h_01HKW6Z36N3JSYEWJZH74M5WWJ=configurar-wechat-en-appsflyer h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab activate-partner=activar-socio h_01HKW6Z36P0EQF829NW3GDXKEN=activar-socio h_01HKW6Z36P806MHV6N3D1N9HW3=nota general-settings=configuraci%C3%B3n-general h_01HKW6Z36P51EG4BW7WA3JGSKN=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6Z36P3D4EPKC6ZZK94YVF=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Z36PA90WEJMFH7BZMD72=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6Z36P73H79MVFXQ29K2M6=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6Z36P95C7CT1J6YS5CQN8=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6Z36PEAPM8RAKB0RM9RES=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
