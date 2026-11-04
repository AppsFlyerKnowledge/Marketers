---
title: Configuración de la campaña de MoEngage
metadata:
  keywords:
    - MoEngage
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
  created_at: '2017-06-25T07:50:18Z'
  edited_at: '2026-08-12T11:59:20Z'
  id: 115003139643
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/115003139643
---
> **De un vistazo:** MoEngage, una plataforma de engagement de clientes de terceros integrada con AppsFlyer, es una plataforma de engagement de clientes agéntica diseñada para un mundo mobile first.

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-moengage" />

## Configuración de MoEngage

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">cómo configurar el encabezado de la página del partner.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** está dividida en diferentes secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En tu primera visita, activa **Activar partner** para configurar la integración. El conmutador debe estar activado mientras trabajes con el partner. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

<div id="general-settings" />

### Configuración general

MoEngage se conecta con AppsFlyer mediante un ID de app único, una App Key y el centro de datos de MoEngage. Si aún no tienes el ID de app y la App Key, debes obtenerlos primero para continuar con la integración:

* **APP\_ID:** Introduce el ID de la app. Para obtenerlo, inicia sesión en tu cuenta de MoEngage desde el menú de la izquierda, y ve a **Configuración** > **Configuración de la app**.
* **Centro de datos de MoEngage:** Especifica el centro de datos de MoEngage con el que te has registrado. Saber más sobre <Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage">los centros de datos en MoEngage</Anchor>.
* **APP\_KEY:** Introduce la clave de API de la app. Para obtenerla, inicia sesión en tu cuenta de MoEngage y ve a **Configuración** > **Analytics**.

![moengage_general_settings_en-us.png](https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png)

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a MoEngage tras las instalaciones de los usuarios. Selecciona una de las siguientes opciones:

* **Desactivado**: No envíes ningún postback de instalación.
* **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks para eventos atribuidos a cualquier partner y para eventos orgánicos.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Nota:**
>
> Como red de todas las instalaciones, MoEngage prefiere recibir postbacks de todas las nuevas instalaciones de tu app desde cualquier fuente, incluidas las orgánicas. MoEngage recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

El **enlace de atribución** no es compatible con la integración con este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los **datos de costos** no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los **ingresos por anuncios** no son compatibles con la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

No se admiten los **permisos** en la integración con este partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJPMX1TXBZY6C94HQ7J85=importante setting-up-moengage=configuraci%C3%B3n-de-moengage h_01H9HWJPMXN58VV9SQQPY4T5HZ=configuraci%C3%B3n-de-moengage h_01H9HWJPMX946NS52DTPAZWVEK=integration-tab activate-partner=activar-socio h_01H9HWJPMX46NV79HHGRRD6D56=activar-socio general-settings=configuraci%C3%B3n-general h_01H9HWJPMXPZ5QV9D08CJMHMHS=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9HWJPMX0TZ496PP8EY3H336=postbacks-predeterminados h_01H9HWJPMX4CHJ9MADEQBSDMGY=nota h_01H9HWJPMXJVWPK67W5X88GYHZ=attribution-link-tab h_01H9HWJPMXQ07XNN8Y79P5DCAN=cost-tab h_01H9HWJPMX8MC1GSD2VD3QQ82Y=ad-revenue-tab h_01H9HWJPMXKYXVCH3HRA2FCPSQ=permissions-tab" />
