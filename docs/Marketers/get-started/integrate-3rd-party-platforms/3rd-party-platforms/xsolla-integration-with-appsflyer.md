---
title: Integración de Xsolla con AppsFlyer
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
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-08-12T11:59:52Z'
  id: 23593013687185
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/23593013687185
---
> **En resumen:** Xsolla, un partner integrado de AppsFlyer, es un partner tecnológico de comercio de juegos especializado en el procesamiento de pagos fuera de las plataformas de aplicaciones tradicionales. La integración entre Xsolla y AppsFlyer permite a Xsolla automatizar las compras de la tienda web y enviar ingresos a AppsFlyer para presentar el ROAS y el LTV completos del juego, incluidas las compras realizadas en la tienda web de Xsolla.

> 🚧 **¡Importante!**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Tipos de integración

Hay dos métodos de integración disponibles con Xsolla:

* [Integración de partners tecnológicos](#configuración-de-la-integración-de-partners-tecnológicos): Esta integración permite a Xsolla enviar compras e ingresos de la tienda web como eventos in-app móviles, mejorando así el ROAS y el LTV de la campaña de aplicaciones móviles más allá de las compras estándar de la tienda de aplicaciones.
* [Prueba la integración del SDK web de PBA](#configuración-de-la-integración-del-sdk-web-de-la-pba): Esta integración permite a Xsolla enviar compras e ingresos a la tienda web como eventos web, lo que permite a AppsFlyer medir el rendimiento de las campañas web y enviar a los usuarios de juegos directamente a la tienda web.

**Requisitos previos:**

* Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.
* Para que la integración funcione correctamente, asegúrate de compartir el ID de usuario de cliente (CUID) con AppsFlyer y de que coincida con el ID de usuario compartido con Xsolla. Esta alineación permite a los usuarios iniciar sesión en la tienda web de Xsolla y garantiza que los datos de los usuarios se envíen con precisión a AppsFlyer.

## Configuración de la integración de partners tecnológicos

**Requisito previo:** Antes de configurar la integración, asegúrate de [ponerte en contacto con el partner](#) y abrir una cuenta con ellos. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activar:** En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla**: En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Selecciona la aplicación correspondiente.
3. En la pestaña **Integración**, selecciona la aplicación para la integración y selecciona **Activar partner**.
4. En la primera visita, tendrás que activar el conmutador **Activar partner** para configurar la integración. El conmutador debe permanecer encendido durante todo el tiempo que se trabaje con Xsolla. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Para ver una descripción detallada del encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración solo hace uso de la pestaña **Integración**.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

#### Activar partner

La configuración se realiza desde la página **Integraciones activas**, pero para encontrar al partner primero debes ir al <Anchor target="_blank" href="/marketers/es/docs/partner-integrations">marketplace</Anchor>. El conmutador debe permanecer encendido durante todo el tiempo que se trabaje con Xsolla. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

#### Privacidad avanzada

Para las aplicaciones de iOS, aparece el selector de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada</Anchor>. Cuando se activa, limita el intercambio de identificadores de usuario con el partner. Ten en cuenta que cuando la opción <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada agregada</Anchor> está activada en la Configuración de la aplicación, la **Privacidad avanzada (para iOS 14.5+ y versiones posteriores)** está activada y bloqueada de forma predeterminada.

#### Postbacks predeterminados

AppsFlyer envía postbacks predeterminados a Xsolla después de las instalaciones de los usuarios. Usa esta sección para <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">definir estos postbacks</Anchor>.

* **Desactivado:** Los postbacks de instalaciones no se envían a Xsolla.  
  **Nota:** La integración de Xsolla con AppsFlyer no requiere el envío de postbacks de instalación. Por lo tanto, se recomienda configurarlo en Desactivado.
* **Todas las fuentes de medios, incluidas las orgánicas:** Los postbacks de instalaciones se envían para los eventos atribuidos a cualquier partner y para los eventos orgánicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### Postbacks de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con tus partners a través de postbacks.

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. Activa **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para añadir un SDK o un evento de servidor a servidor a la lista.
3. Completa los siguientes parámetros:

| Nombre del parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br /><br />**Nota:**<ul><li>Para Xsolla, asegúrate de agregar el evento `af_login` o cualquier otro evento que represente el inicio de sesión del usuario en la aplicación móvil, como se muestra en la captura de pantalla anterior.</li></ul> |
| **Asignado al evento de partner** | Ingresa el nombre del evento correspondiente que deseas enviar a Xsolla. El nombre de Xsolla es flexible y se puede usar cualquier nombre en este campo. |
| **para usuarios de** | Selecciona **Todas las fuentes de medios, incluidas las orgánicas** para enviar postbacks de los eventos atribuidos a cualquier partner y los eventos orgánicos. |
| **incluyendo** | <ul><li>**Sin valores ni ingresos**: Envía solo el evento en sí, sin ningún parámetro (valores o ingresos).</li><li>**Valores y sin ingresos**: Envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: Envía todos los parámetros del evento, **incluido** el valor de los ingresos (si existe en el evento).</li></ul>Nota: La integración de Xsolla con AppsFlyer no requiere el envío de valores ni ingresos. Por lo tanto, se aplica cualquier opción seleccionada. |

4. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de atribución no están disponibles para Xsolla.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Los datos de costos no se admiten en la integración con Xsolla.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos publicitarios">

Los datos de ingresos publicitarios no se admiten en la integración con Xsolla.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Xsolla.

</Accordion>

## Configuración de la integración del SDK web de la PBA

Esta integración permite disponer de datos e insights actuales sobre el LTV para analizar el rendimiento de la aplicación dentro del dashboard de PBA.

**Configura la integración:**

1. **En AppsFlyer:** <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Agrega la aplicación Xsolla</Anchor>. Selecciona <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web-pba">Web (PBA)</Anchor> como plataforma e ingresa los siguientes detalles:
   * Usa tu dominio de tienda web como URL de la aplicación web. Por ejemplo, si tu dominio de tienda web es [www.webshop.com,](http://www.webshop.com,) utilízalo como URL de tu aplicación web.
   * Usa cualquier valor como nombre de la aplicación.
2. **En AppsFlyer:** <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#add-brand-bundle">Agrega el paquete</Anchor> de Xsolla con los siguientes detalles:
   1. Ingresa cualquier nombre de paquete como el nombre del paquete.
   2. Selecciona la aplicación web que creaste en el paso anterior como la aplicación web del paquete.
3. **En Xsolla:** Conecta AppsFlyer con tu cuenta de publisher de Xsolla:
   1. Abre tu proyecto en tu <Anchor target="_blank" href="https://publisher.xsolla.com/">cuenta de publisher</Anchor>.
   2. Selecciona tu sitio y haz clic en **Configurar**.
   3. En la pestaña **Configuración del sitio**, ve a la sección **Aplicaciones**.
   4. En el bloque **AppsFlyer**, haz clic en **Conectar**.  
      [![xsolla-connect.jpg](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)
   5. En el campo **Clave de desarrollador** de AppsFlyer, ingresa la clave del desarrollador web de AppsFlyer. Mira a continuación cómo [encontrar esta clave en AppsFlyer](/docs/xsolla-integration-with-appsflyer#cómo-encontrar-la-clave-del-desarrollador-web-en-appsflyer).
   6. Haz clic en **Conectar**.

#### Cómo encontrar la clave del desarrollador web en AppsFlyer

1. Desde la página **Mis aplicaciones**, haz clic en **Ver paquetes de marca**.
2. Haz clic en el icono Copiar en la fila del paquete Xsolla.

![xsolla-brand-bundle2.jpg](https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg)

## Identificación de eventos de Xsolla en AppsFlyer

### Integración de partners tecnológicos (S2S):

Xsolla envía a AppsFlyer 2 eventos in-app:

* **xsolla-billing-payment** - Artículo comprado
* **xsolla-billing-refund** - Reembolso de compra de artículos

Ambos eventos son parte de los eventos in-app de la aplicación móvil.

### Integración del SDK web:

Xsolla envía a AppsFlyer múltiples eventos web personalizados según la actividad específica del anunciante. El más importante se llama "COMPRA" y contiene ingresos.  
Los eventos web de Xsolla aparecerán en los reportes de DataLocker de raw "Eventos web" y atribución web de PBA.

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

Compatibilidad con PC/consolas: la integración de AppsFlyer con Xsolla no es compatible con aplicaciones de PC/consolas en esta fase.

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Documentación de Xsolla</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=importante integration-types=tipos-de-integraci%C3%B3n h_01J3DB8MCNQKKKCV1M39KN7Q0H=tipos-de-integraci%C3%B3n setting-up-xsolla=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-partners-tecnol%C3%B3gicos h_01HST42K52JKQ70F7Y5PHDZAZ5=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-partners-tecnol%C3%B3gicos h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=activar-partner h_01HST42K52RCTSGRNRCJ1C70NP=activar-partner advanced-privacy=privacidad-avanzada h_01HST42K52BBJ6JS5KM0WCN6CF=privacidad-avanzada default-postbacks=postbacks-predeterminados h_01HST47F5BXWV5W8BNHS9M2MTN=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postbacks-de-eventos-in-app h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-del-sdk-web-de-la-pba h_01J3DEZZHDPSRZRXDV6FD4HY6Q=configuraci%C3%B3n-de-la-integraci%C3%B3n-del-sdk-web-de-la-pba finding-the-web-dev-key-in-appsflyer=c%C3%B3mo-encontrar-la-clave-del-desarrollador-web-en-appsflyer h_01J3F247QEAFGRW7CEP941KZE9=c%C3%B3mo-encontrar-la-clave-del-desarrollador-web-en-appsflyer identifying-xsollas-events-in-appsflyer=identificaci%C3%B3n-de-eventos-de-xsolla-en-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=identificaci%C3%B3n-de-eventos-de-xsolla-en-appsflyer tech-partner-s2s-integration=integraci%C3%B3n-de-partners-tecnol%C3%B3gicos-s2s h_01JMHXS5MZ7B781WNNVYMDGGFY=integraci%C3%B3n-de-partners-tecnol%C3%B3gicos-s2s web-sdk-integration=integraci%C3%B3n-del-sdk-web h_01JMHXX7VBPPS7GQ0VBGWRPT7X=integraci%C3%B3n-del-sdk-web h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=consulta-tambi%C3%A9n" />
