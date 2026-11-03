---
title: Configuración de la campaña de anuncios de UC Toutiao
metadata:
  keywords:
    - Advertisers
    - UC Toutiao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-25T05:41:49Z'
  edited_at: '2026-09-17T00:26:26Z'
  id: 115004843026
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115004843026
---
> **De un vistazo:** UC Toutiao Ads, un partner integrado de ad network de AppsFlyer, es una de las principales aplicaciones agregadoras de noticias de China.

## Configuración de UC Toutiao

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partner</Anchor>.

La ventana de configuración de UC Toutiao incluye 2 pestañas activas: integración y enlace de atribución.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

De forma predeterminada, UC Toutiao recibe postbacks solo de eventos de nueva instalación atribuidos a él.

![uc-toutiao-integration.png](https://files.readme.io/1ed78bd49d9a49d134f5c48655765ad205515752d88528a0a453bd3a091492c0-360002074869.png)

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a UC Toutiao mediante postbacks.

[![](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)

1. Vuelve a establecer aquí el ID de red de UC Toutiao
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define UC Toutiao.  <br />Obtén el ID de evento correspondiente de UC Toutiao y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada** - AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada** - AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a UC Toutiao para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de UC Toutiao. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

[![UC_Toutiao_pestaña_enlace_de_atribución.png](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas de UC Toutiao.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de UC Toutiao.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define los nombres de los anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, en campañas específicas de UC Toutiao.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-params.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a UC Toutiao.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics aquí</Anchor>.

![uc-toutiao-click-through.png](https://files.readme.io/8128e80c365aa223105260a25aa99a61bd9eeccdf19d311804ed3e66b744ef39-360002074929.png)

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a UC Toutiao para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

No hay ninguna configuración de permisos disponible para este partner.

</Accordion>

## Crear conversión en uc toutiao ads

Inicia sesión en UC Toutiao Ads (<Anchor target="_blank" href="https://e.uc.cn/">https://e.uc.cn/</Anchor>) y ve a **Click Promotion Tools** >> **Click Conversion Tools** >> **Create Conversion**

![Toutiao_4.png](https://files.readme.io/40e4c3f26faf2cf928fe874398a7e505d100e717669867fc8a55b8b9fec1f021-115016024743.png)

Introduce la información relacionada con la aplicación >> **Click Confirm** >> **Generate 2-dimension code**

Aplicación de Android:

![Toutiao_5.png](https://files.readme.io/8db1f985882f847aad08e4e46710bd9af8a95b62e0a0b488d5242879cd11b7bd-115015832006.png)

iOS App:

![Toutiao_6.png](https://files.readme.io/18b8ba97b8792db66ec4874269bf1b6ccb21ad68016a57e52534f4e97835cc92-115016025123.png)

Usa la app de Alipay o la app de Dingding para escanear el código bidimensional de 2 dimensiones e instalar tu App. Completa la prueba de conversión y, a continuación, el estado de esta conversión pasará a activo.

6. Crea tus anuncios

Crea tu anuncio yendo a: **Nivel del anuncio** >> **Sección de configuración de puja** >> **Habilita la conversión**

![Toutiao_7.png](https://files.readme.io/f2c49499432c3c358d737544ea02cb5b1e634244313606a62102707dd8a3c31e-115015832146.png)

<div data-zendesk-anchors="setting-up-uc-toutiao=configuraci%C3%B3n-de-uc-toutiao h_01HKW6Y1PVGS22BXK54VW8C488=configuraci%C3%B3n-de-uc-toutiao h_01HKW6Y1PWJEJHCCY5WM8AYNGE=integration-tab activate-partners=activar-los-partners h_01HKW6Y1PWX3TMM41S78MJ21C1=activar-los-partners default-postbacks=postbacks-predeterminados h_01HKW6Y1PWRZNRX6061KFECTDN=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Y1PWRMK1H7QCW1GQWAA7=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Y1PW95EWPGP09CCJF97M=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6Y1PWVTGGNX96AWVZJ9PP=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6Y1PWEW2FWN8K5S8DKQJJ=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6Y1PWKPJ09G70XMQG8H1S=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6Y1PWFS5X835MYJG0CVJ0=cost-tab h_01HKW6Y1PWJW4EW33MYRDN2FJB=ad-revenue-tab h_01HKW6Y1PWDWN4KWMA1KX5FYDT=permissions-tab create-conversion-at-uc-toutiao-ads=crear-conversi%C3%B3n-en-uc-toutiao-ads h_01HKW6Y1PWVMM70F6MJVCJYKT3=crear-conversi%C3%B3n-en-uc-toutiao-ads" />
