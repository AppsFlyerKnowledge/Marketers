---
title: Integración de Swrve con AppsFlyer
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-08-22T00:11:58Z'
  id: 207040656
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207040656
---
> **At a glance:** Swrve, un partner integrado de AppsFlyer, es un motor de interacción con clientes multiplataforma que permite a los anunciantes ofrecer interacciones específicas, personales y optimizadas a los usuarios finales:

* Optimización dinámica y pruebas del contenido principal de la aplicación
* Campañas in-app y de notificaciones push
* Correo electrónico

Junto con AppsFlyer, Swrve ofrece una solución completa del ciclo de vida para maximizar el ROI de los gastos en desarrollo y adquisición, y proporciona experiencias de usuario excelentes a lo largo de todo el recorrido en la aplicación móvil. Esto incluye personalizar la experiencia del usuario en función de la fuente de adquisición compartida entre las dos plataformas, lo que significa que se puede mostrar a los usuarios contenido específico para su recorrido desde el momento en que abren la aplicación por primera vez.

La integración funciona notificando a Swrve las instalaciones a su API mediante su API REST. Para ello, tendrás que configurar un postback del servidor en tu cuenta de AppsFlyer para cada una de tus aplicaciones móviles.

> 🚧 **Important**
>
> **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="integrating-swrve-and-appsflyer" />

## Integración de Swrve y AppsFlyer

Configurar un postback que permita a Swrve medir el LTV y el comportamiento de los usuarios para diferentes fuentes de adquisición:

**Paso 1**: Después de inicializar Swrve, establece el ID del usuario (antes de cualquier llamada al SDK de AppsFlyer) con lo siguiente:

<Tabs>
<Tab title="Para Android">

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

</Tab>

<Tab title="Para iOS">

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

</Tab>

<Tab title="Para Unity">

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

</Tab>
</Tabs>

**Paso 2**: Configura un postback en tu dashboard de AppsFlyer realizando las siguientes acciones:

<div id="setting-up-swrve" />

## Configuración de Swrve

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Configurar la integración de ASA**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Swrve solo utiliza la pestaña **integración**.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activate Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**ID de la aplicación y clave API**

Swrve se conecta con AppsFlyer mediante un ID de aplicación único y una clave API. Si aún no los tienes, debes obtenerlos de Swrve para continuar con la integración.

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

Realiza los siguientes pasos, según sea necesario:

* Introduce el **APP\_ID**
* Introduce la **api\_key**
* Selecciona **UE** para los clientes de la UE
* Selecciona **Uso compartido avanzado de datos** para enviar la siguiente información adicional a Swrve: cost\_value, canal, keywords, siteID y c (campaña)

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Swrve tras las instalaciones de los usuarios. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks a Swrve de cualquier usuario que descargue la app.

Haz clic en **Save**

Una vez guardado, AppsFlyer empieza a enviar los siguientes datos a Swrve para cada instalación orgánica y no orgánica:

* api\_key
* ID de usuario de Swrve tal como se ha configurado en el SDK
* Fuente de medios
* Nombre de la campaña

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Swrve.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Swrve.

</Accordion>

<div id="swrve-reporting-with-appsflyer-data" />

## Reportes de Swrve con datos de AppsFlyer

Después de configurar los postbacks del servidor para enviar información de atribución desde AppsFlyer a Swrve, puedes ver los datos de adquisición en la plataforma de Swrve y utilizar toda la gama de funcionalidades de targeting y testing de Swrve.

La página principal del dashboard de tu aplicación incluye de un vistazo toda la información vital de tu aplicación. Desde esta página, puedes seguir utilizando las funciones de testing, targeting e informes seleccionando las pestañas correspondientes en la barra de navegación principal.

![Gráfico de adquisición del dashboard de Swrve](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)
![Tabla de datos de adquisición del dashboard de Swrve](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="integrating-swrve-and-appsflyer=integraci%C3%B3n-de-swrve-y-appsflyer h_01H9HWK5DM1K9P5XXC6S7ENAGV=integraci%C3%B3n-de-swrve-y-appsflyer setting-up-swrve=configuraci%C3%B3n-de-swrve h_01H9HWK5DMS8HAK25BF5EXZT51=configuraci%C3%B3n-de-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=activar-socio h_01H9HWK5DN375XJVHQCZ8Y3K13=activar-socio general-settings=configuraci%C3%B3n-general h_01H9HWK5DN0XK2E0HXS61GRECE=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9HWK5DNH6SYY8T9NX09MRYS=postbacks-predeterminados h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=reportes-de-swrve-con-datos-de-appsflyer h_01H9HWK5DN3QB9V593EV566GAQ=reportes-de-swrve-con-datos-de-appsflyer" />
